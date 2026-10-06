<template>
  <div class="container mt-4 text-center">
    <div class="card glass-card p-4 mx-auto" style="max-width: 500px;">
      <h3 class="mb-3 text-primary-custom">Validasi Kehadiran</h3>
      
      <!-- Video Feed untuk Face Recognition -->
      <div class="video-container mb-3 position-relative rounded overflow-hidden">
        <video ref="videoEl" autoplay muted playsinline class="w-100"></video>
      </div>

      <p class="text-muted"><i class="fas fa-map-marker-alt"></i> Akurasi Lokasi: {{ gpsStatus }}</p>
      
      <button @click="captureAndSubmit" class="btn btn-primary w-100 mb-2 rounded-pill shadow-sm" style="background-color: #2C3E50; border:none;">
        <i class="fas fa-camera"></i> Absen Sekarang
      </button>
      
      <!-- Alur Lihat Riwayat & Logout[cite: 2] -->
      <div class="d-flex justify-content-between mt-3">
        <button class="btn btn-sm btn-outline-info">Lihat Riwayat</button>
        <button class="btn btn-sm btn-outline-danger">Logout</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';

const videoEl = ref(null);
const gpsStatus = ref('Mencari lokasi...');
const coordinates = ref(null);

onMounted(async () => {
  // Akses Kamera (Responsive Mobile & Desktop)
  try {
    const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" } });
    videoEl.value.srcObject = stream;
  } catch (err) {
    alert('Akses kamera diperlukan untuk absen.');
  }

  // Akses GPS
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(
      pos => {
        coordinates.value = { lat: pos.coords.latitude, lng: pos.coords.longitude };
        gpsStatus.value = 'Lokasi ditemukan \u2713';
      },
      err => gpsStatus.value = 'Gagal mendapat lokasi \u2717',
      { enableHighAccuracy: true }
    );
  }
});

const captureAndSubmit = async () => {
  if (!coordinates.value) return alert('Tunggu hingga lokasi GPS ditemukan!');
  
  // Capture frame dari video
  const canvas = document.createElement('canvas');
  canvas.width = videoEl.value.videoWidth;
  canvas.height = videoEl.value.videoHeight;
  canvas.getContext('2d').drawImage(videoEl.value, 0, 0);
  const faceBase64 = canvas.toDataURL('image/jpeg');

  try {
    // Alur Absensi dicatat dalam tabel[cite: 1]
    const res = await axios.post('http://localhost:3000/api/absen', {
      id_user: 1, // Didapat dari session JWT saat Login[cite: 2]
      faceBase64,
      latitude: coordinates.value.lat,
      longitude: coordinates.value.lng
    });
    alert(res.data.message);
  } catch (error) {
    alert(error.response?.data?.message || 'Gagal absen');
  }
};
</script>

<style scoped>
.glass-card {
  background: rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(15px);
  border: 1px solid rgba(255, 255, 255, 0.5);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}
.dark-mode .glass-card {
  background: rgba(30, 30, 40, 0.6);
  border: 1px solid rgba(255, 255, 255, 0.1);
}
</style>