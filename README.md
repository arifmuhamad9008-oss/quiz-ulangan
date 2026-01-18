document.getElementById('submit-btn').addEventListener('click', function() {
    const answers = {
        q1: 'a', // Henri Fayol
        q2: 'a', // Perencanaan, dll.
        q3: 'a', // Jumlah bawahan
        q4: 'a', // Frederick Taylor
        q5: 'a', // Koordinasi tim virtual (relevan untuk UT)
        q6: 'a'  // Memastikan kegiatan sesuai rencana
    };
    
    let score = 0;
    let totalQuestions = Object.keys(answers).length;
    
    for (let key in answers) {
        const selected = document.querySelector(`input[name="${key}"]:checked`);
        if (selected && selected.value === answers[key]) {
            score++;
        }
    }
    
    const resultDiv = document.getElementById('result');
    const scoreP = document.getElementById('score');
    const feedbackP = document.getElementById('feedback');
    
    scoreP.textContent = `Skor Anda: ${score} dari ${totalQuestions}`;
    
    if (score === totalQuestions) {
        feedbackP.textContent = 'Luar biasa! Anda siap menghadapi ujian Manajemen di Universitas Terbuka.';
    } else if (score >= totalQuestions / 2) {
        feedbackP.textContent = 'Bagus! Tinjau materi lagi, terutama konteks jarak jauh.';
    } else {
        feedbackP.textContent = 'Perlu belajar lebih giat. Akses modul UT dan latihan soal tambahan!';
    }
    
    resultDiv.style.display = 'block';
});
