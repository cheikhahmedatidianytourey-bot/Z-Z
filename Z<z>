<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Z Studio Ultimate &bull; Core Z^Z (Zalapuissance Z)</title>
    <style>
        :root {
            --bg-color: #02040a;
            --panel-bg: rgba(6, 12, 28, 0.96);
            --border-color: #00f0ff;
            --accent-color: #7000ff;
            --text-color: #e0f7ff;
            --glow-color: rgba(0, 240, 255, 0.4);
            --font-family: 'Segoe UI', Roboto, sans-serif;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; user-select: none; }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: var(--font-family);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            background-image: 
                radial-gradient(circle at 50% 50%, rgba(112, 0, 255, 0.22) 0%, transparent 80%),
                linear-gradient(rgba(0, 240, 255, 0.04) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 240, 255, 0.04) 1px, transparent 1px);
            background-size: 100% 100%, 35px 35px, 35px 35px;
        }

        header {
            padding: 18px 28px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-color);
            box-shadow: 0 0 25px var(--glow-color);
            background: rgba(2, 4, 10, 0.98);
        }

        .logo-area { display: flex; align-items: center; gap: 16px; }

        .logo-badge {
            background: linear-gradient(45deg, var(--accent-color), var(--border-color));
            color: #fff;
            width: 48px;
            height: 48px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            font-weight: 900;
            border-radius: 8px;
            box-shadow: 0 0 20px var(--border-color);
        }

        h1 { font-size: 1.5rem; letter-spacing: 3px; text-transform: uppercase; color: #fff; }
        .subtitle { font-size: 0.75rem; color: var(--border-color); letter-spacing: 2px; }

        .container {
            display: flex;
            flex: 1;
            padding: 24px;
            gap: 24px;
            max-width: 1600px;
            margin: 0 auto;
            width: 100%;
        }

        @media (max-width: 1024px) { .container { flex-direction: column; } }

        .panel {
            background: var(--panel-bg);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 22px;
            backdrop-filter: blur(16px);
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.85);
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .controls-panel { flex: 1; min-width: 340px; }
        .viewport-panel { flex: 2; display: flex; flex-direction: column; align-items: center; justify-content: center; }

        .form-group { display: flex; flex-direction: column; gap: 6px; }
        label { font-size: 0.8rem; text-transform: uppercase; letter-spacing: 1.5px; color: var(--border-color); font-weight: bold; }

        textarea, select, input[type="range"] {
            background: rgba(0, 12, 30, 0.95);
            border: 1px solid rgba(0, 240, 255, 0.45);
            border-radius: 6px;
            color: #fff;
            padding: 12px;
            font-family: inherit;
            font-size: 0.9rem;
            outline: none;
        }

        textarea { resize: vertical; min-height: 110px; }
        .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }

        .btn {
            background: linear-gradient(45deg, var(--accent-color), var(--border-color));
            border: none;
            border-radius: 6px;
            color: #fff;
            padding: 16px;
            font-size: 1rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            box-shadow: 0 0 20px rgba(112, 0, 255, 0.6);
        }

        .btn:hover { box-shadow: 0 0 30px var(--border-color); }

        .canvas-wrapper {
            position: relative;
            width: 100%;
            aspect-ratio: 16/9;
            background: #000;
            border: 2px solid var(--border-color);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 0 35px rgba(0, 240, 255, 0.3);
        }

        canvas, video { width: 100%; height: 100%; display: block; object-fit: cover; }
        video { display: none; }

        .hud-overlay {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none; padding: 14px;
            display: flex; flex-direction: column; justify-content: space-between;
        }

        .hud-header, .hud-footer {
            display: flex; justify-content: space-between;
            font-family: monospace; font-size: 0.8rem; color: var(--border-color);
            text-shadow: 0 0 8px var(--glow-color);
        }

        .progress-bar-container {
            width: 100%; height: 6px; background: rgba(255, 255, 255, 0.1);
            border-radius: 3px; overflow: hidden; margin-top: 6px;
        }

        .progress-bar {
            height: 100%; width: 0%;
            background: linear-gradient(90deg, var(--accent-color), var(--border-color));
            transition: width 0.1s linear;
        }

        .status-badge {
            padding: 3px 8px; border-radius: 4px; font-size: 0.75rem;
            font-weight: bold; text-transform: uppercase;
            background: rgba(0, 240, 255, 0.15); border: 1px solid var(--border-color); color: var(--border-color);
        }

        .export-actions { display: flex; gap: 10px; width: 100%; margin-top: 14px; }

        .btn-secondary {
            background: rgba(0, 240, 255, 0.1); border: 1px solid var(--border-color);
            color: var(--border-color); flex: 1; padding: 14px; border-radius: 6px;
            cursor: pointer; font-weight: bold; text-transform: uppercase;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-area">
            <div class="logo-badge">Z&#x207D;Z&#x207E;</div>
            <div>
                <h1>Z Studio Ultimate</h1>
                <div class="subtitle">CORE Z^Z &bull; ZALAPUISSANCE Z &bull; PROJECTION FUTUR</div>
            </div>
        </div>
    </header>

    <div class="container">
        <div class="panel controls-panel">
            <div class="form-group">
                <label for="prompt">Scénario &amp; Narration Z^Z</label>
                <textarea id="prompt">[AWA] : Diamniadio, supercalculateur quantique et tours bioclimatiques opérationnels.
[CHEIKH] : Nos infrastructures allient tradition et design automobile futuriste VELTŪR.
[TER-MAGLEV] : Départ imminent de la navette à lévitation magnétique.
[SUNU-NDANANE] : L'IA souveraine pilote l'économie décentralisée à 100%.
[GRANDE MURAILLE VERTE] : Le bouclier forestier régénère tout notre écosystème.</textarea>
            </div>

            <div class="form-group">
                <label for="timeline">Horizon Temporel : <span id="yearVal">2060</span></label>
                <input type="range" id="timeline" min="2060" max="2100" value="2060" oninput="document.getElementById('yearVal').innerText = this.value">
            </div>

            <div class="grid-2">
                <div class="form-group">
                    <label for="language">Voix Neuronale HD</label>
                    <select id="language">
                        <option value="fr-FR">Français (Studio HD)</option>
                        <option value="wo-SN">Wolof (Natif HD)</option>
                        <option value="en-US">English (Studio HD)</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="duration">Durée de Rendu</label>
                    <select id="duration">
                        <option value="15" selected>15 Sec (Teaser)</option>
                        <option value="60">1 Min (Séquence)</option>
                    </select>
                </div>
            </div>

            <div class="grid-2">
                <div class="form-group">
                    <label for="camera">Mise en Scène 3D</label>
                    <select id="camera">
                        <option value="megacity">Survol Gratte-Ciel Bioclimatiques</option>
                        <option value="vehicles">Focus VELTŪR &amp; Navettes Maglev</option>
                        <option value="hologram">Hologramme Awa &amp; Cheikh</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="style">Ambiance Visuelle</label>
                    <select id="style">
                        <option value="quantum">Quantique Z^Z (Bleu/Violet)</option>
                        <option value="cyberpunk">Cyberpunk Néon Doré</option>
                    </select>
                </div>
            </div>

            <button id="generateBtn" class="btn">LANCER LE TOURNAGE Z^Z</button>

            <div class="progress-bar-container">
                <div id="progressBar" class="progress-bar"></div>
            </div>
        </div>

        <div class="panel viewport-panel">
            <div class="canvas-wrapper">
                <canvas id="renderCanvas" width="1280" height="720"></canvas>
                <video id="videoPlayer" controls playsinline></video>
                <div class="hud-overlay">
                    <div class="hud-header">
                        <div>Z^Z ENGINE // CORE ZALAPUISSANCE</div>
                        <div>PROJECTION FUTUR &bull; SANS FILIGRANE</div>
                    </div>
                    <div class="hud-footer">
                        <div>STATUT : <span id="statusText" class="status-badge">PRÊT</span></div>
                        <div id="timerText">00:00 / 00:00</div>
                    </div>
                </div>
            </div>

            <div class="export-actions">
                <button id="downloadBtn" class="btn-secondary" disabled>TÉLÉCHARGER LE FILM BRUT (.WEBM)</button>
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('renderCanvas');
        const videoPlayer = document.getElementById('videoPlayer');
        const ctx = canvas.getContext('2d');
        const generateBtn = document.getElementById('generateBtn');
        const downloadBtn = document.getElementById('downloadBtn');
        const progressBar = document.getElementById('progressBar');
        const statusText = document.getElementById('statusText');
        const timerText = document.getElementById('timerText');

        let isRendering = false;
        let mediaRecorder;
        let recordedChunks = [];
        let synth = window.speechSynthesis;

        function drawIdleState() {
            canvas.style.display = 'block';
            videoPlayer.style.display = 'none';
            ctx.fillStyle = '#02040a';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = 'rgba(0, 240, 255, 0.15)';
            for(let i = 0; i < canvas.width; i += 120) {
                let h = 220 + (i % 280);
                ctx.fillRect(i + 15, canvas.height - h, 80, h);
            }

            ctx.fillStyle = '#00f0ff';
            ctx.font = 'bold 22px monospace';
            ctx.textAlign = 'center';
            ctx.fillText('Z STUDIO CORE Z^Z - ZALAPUISSANCE Z', canvas.width / 2, canvas.height / 2 - 20);
            ctx.fillStyle = 'rgba(255, 255, 255, 0.7)';
            ctx.font = '13px monospace';
            ctx.fillText('PRÊT AU TOURNAGE &bull; GRATTE-CIEL &bull; VELTŪR &bull; AUDIO INCLUS', canvas.width / 2, canvas.height / 2 + 15);
        }
        drawIdleState();

        generateBtn.addEventListener('click', async () => {
            if (isRendering) return;

            const prompt = document.getElementById('prompt').value;
            const lang = document.getElementById('language').value;
            const targetDuration = parseInt(document.getElementById('duration').value);
            const visualStyle = document.getElementById('style').value;
            const targetYear = document.getElementById('timeline').value;

            isRendering = true;
            generateBtn.disabled = true;
            downloadBtn.disabled = true;
            canvas.style.display = 'block';
            videoPlayer.style.display = 'none';
            statusText.innerText = "TOURNAGE EN COURS (Z^Z)";
            recordedChunks = [];

            const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            const dest = audioCtx.createMediaStreamDestination();
            
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.type = 'sine';
            osc.frequency.setValueAtTime(75, audioCtx.currentTime);
            gain.gain.setValueAtTime(0.025, audioCtx.currentTime);
            osc.connect(gain);
            gain.connect(dest);
            osc.connect(audioCtx.destination);
            osc.start();

            if (synth) {
                synth.cancel();
                const utterance = new SpeechSynthesisUtterance(prompt.replace(/\[.*?\]/g, ''));
                utterance.lang = lang;
                utterance.rate = 0.95;
                synth.speak(utterance);
            }

            const canvasStream = canvas.captureStream(60);
            const combinedStream = new MediaStream([
                ...canvasStream.getVideoTracks(),
                ...dest.stream.getAudioTracks()
            ]);

            const options = MediaRecorder.isTypeSupported('video/webm;codecs=vp9') 
                ? { mimeType: 'video/webm;codecs=vp9' } 
                : { mimeType: 'video/webm' };

            mediaRecorder = new MediaRecorder(combinedStream, options);
            
            mediaRecorder.ondataavailable = (e) => {
                if (e.data.size > 0) recordedChunks.push(e.data);
            };

            mediaRecorder.onstop = () => {
                const blob = new Blob(recordedChunks, { type: 'video/webm' });
                const url = URL.createObjectURL(blob);
                
                canvas.style.display = 'none';
                videoPlayer.style.display = 'block';
                videoPlayer.src = url;

                downloadBtn.disabled = false;
                downloadBtn.onclick = () => {
                    const a = document.createElement('a');
                    a.href = url;
                    a.download = `Z_Core_ZZ_${targetYear}_${Date.now()}.webm`;
                    a.click();
                };
                statusText.innerText = "FILM PRÊT AU TÉLÉCHARGEMENT";
                generateBtn.disabled = false;
                isRendering = false;
                try { osc.stop(); } catch(e) {}
            };

            mediaRecorder.start();

            const startTime = Date.now();

            function renderLoop() {
                const elapsed = (Date.now() - startTime) / 1000;
                const progress = Math.min((elapsed / targetDuration) * 100, 100);

                progressBar.style.width = `${progress}%`;

                const mins = Math.floor(elapsed / 60).toString().padStart(2, '0');
                const secs = Math.floor(elapsed % 60).toString().padStart(2, '0');
                const tMins = Math.floor(targetDuration / 60).toString().padStart(2, '0');
                const tSecs = Math.floor(targetDuration % 60).toString().padStart(2, '0');
                timerText.innerText = `${mins}:${secs} / ${tMins}:${tSecs}`;

                ctx.fillStyle = visualStyle === 'cyberpunk' ? '#110226' : '#010c22';
                ctx.fillRect(0, 0, canvas.width, canvas.height);

                const time = elapsed * 1.5;

                for (let i = 0; i < canvas.width; i += 100) {
                    let towerHeight = 260 + Math.sin(i * 0.1) * 130;
                    let grad = ctx.createLinearGradient(i, canvas.height - towerHeight, i, canvas.height);
                    grad.addColorStop(0, visualStyle === 'cyberpunk' ? 'rgba(255, 0, 127, 0.35)' : 'rgba(0, 240, 255, 0.3)');
                    grad.addColorStop(1, 'rgba(2, 4, 10, 0.95)');
                    ctx.fillStyle = grad;
                    ctx.fillRect(i + 10, canvas.height - towerHeight, 75, towerHeight);
                }

                ctx.strokeStyle = '#00ffcc';
                ctx.lineWidth = 3;
                for (let v = 0; v < 4; v++) {
                    let carX = (time * 200 + v * 320) % (canvas.width + 200) - 100;
                    let carY = canvas.height - 85 - (v * 40);
                    ctx.beginPath();
                    ctx.moveTo(carX, carY);
                    ctx.lineTo(carX + 70, carY - 5);
                    ctx.lineTo(carX + 50, carY - 18);
                    ctx.lineTo(carX + 15, carY - 18);
                    ctx.closePath();
                    ctx.fillStyle = '#00f0ff';
                    ctx.fill();
                    ctx.stroke();
                }

                ctx.strokeStyle = visualStyle === 'cyberpunk' ? '#ff007f' : '#00f0ff';
                ctx.lineWidth = 2;
                ctx.beginPath();
                ctx.arc(canvas.width / 2, canvas.height / 2 - 30, 95 + Math.sin(time * 3) * 8, 0, Math.PI * 2);
                ctx.stroke();

                ctx.fillStyle = '#ffffff';
                ctx.font = 'bold 18px monospace';
                ctx.textAlign = 'center';
                ctx.fillText(`“ SÉNÉGAL ${targetYear} : Z^Z CORE ZALAPUISSANCE ”`, canvas.width / 2, canvas.height - 45);

                if (elapsed < targetDuration) {
                    requestAnimationFrame(renderLoop);
                } else {
                    mediaRecorder.stop();
                    if (synth) synth.cancel();
                }
            }

            renderLoop();
        });
    </script>
</body>
</html>
