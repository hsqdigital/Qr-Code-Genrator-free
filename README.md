<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>QRCodePro - Free QR Code Generator | Create Custom QR Codes</title>
    <meta name="description" content="Free QR Code Generator - Create custom QR codes for URLs, websites, WhatsApp, videos, and more. Download high-quality QR codes instantly.">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.15);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .logo {
            font-size: 3em;
            margin-bottom: 10px;
        }

        .header h1 {
            color: #2c3e50;
            font-size: 2.8em;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .header p {
            color: #7f8c8d;
            font-size: 1.2em;
            margin-bottom: 30px;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }

        .input-section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 15px;
            border: 1px solid #e9ecef;
        }

        .tab-buttons {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .tab-btn {
            padding: 12px 20px;
            background: white;
            border: 2px solid #e9ecef;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            flex: 1;
            min-width: 120px;
            text-align: center;
        }

        .tab-btn.active {
            background: #667eea;
            color: white;
            border-color: #667eea;
        }

        .tab-btn:hover {
            border-color: #667eea;
        }

        .input-group {
            margin-bottom: 20px;
        }

        .input-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #2c3e50;
        }

        .url-input {
            width: 100%;
            padding: 15px 20px;
            font-size: 16px;
            border: 2px solid #ddd;
            border-radius: 10px;
            outline: none;
            transition: all 0.3s ease;
        }

        .url-input:focus {
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
        }

        .customization-options {
            background: white;
            padding: 25px;
            border-radius: 10px;
            border: 1px solid #e9ecef;
            margin-top: 20px;
        }

        .option-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 15px;
        }

        .color-picker {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .color-picker input {
            width: 60px;
            height: 40px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .generate-btn {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
        }

        .generate-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .generate-btn:disabled {
            background: #bdc3c7;
            cursor: not-allowed;
            transform: none;
        }

        .preview-section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 15px;
            border: 1px solid #e9ecef;
            text-align: center;
        }

        .qr-preview {
            margin: 30px auto;
            padding: 30px;
            background: white;
            border-radius: 15px;
            display: inline-block;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border: 1px solid #e9ecef;
            min-height: 300px;
            min-width: 300px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .qr-placeholder {
            color: #bdc3c7;
            font-size: 1.1em;
        }

        .download-options {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .download-btn {
            padding: 15px 30px;
            background: #27ae60;
            color: white;
            border: none;
            border-radius: 25px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .download-btn:hover {
            background: #219a52;
            transform: translateY(-2px);
        }

        .download-btn.png {
            background: #e74c3c;
        }

        .download-btn.png:hover {
            background: #c0392b;
        }

        .download-btn.svg {
            background: #3498db;
        }

        .download-btn.svg:hover {
            background: #2980b9;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 50px 0;
        }

        .feature-card {
            background: white;
            padding: 25px;
            border-radius: 12px;
            text-align: center;
            border: 1px solid #e9ecef;
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
        }

        .feature-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
        }

        .feature-card h3 {
            color: #2c3e50;
            margin-bottom: 10px;
        }

        .feature-card p {
            color: #7f8c8d;
            line-height: 1.5;
        }

        .ad-section {
            background: linear-gradient(135deg, #fff3cd 0%, #ffeaa7 100%);
            padding: 25px;
            border-radius: 15px;
            margin: 40px 0;
            text-align: center;
            border: 2px dashed #f39c12;
        }

        .ad-section h3 {
            color: #e67e22;
            margin-bottom: 10px;
        }

        .premium-btn {
            padding: 12px 30px;
            background: #e74c3c;
            color: white;
            border: none;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 15px;
        }

        .premium-btn:hover {
            background: #c0392b;
            transform: translateY(-2px);
        }

        .loading {
            text-align: center;
            padding: 20px;
            display: none;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #667eea;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto 15px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid #e9ecef;
            color: #7f8c8d;
        }

        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            
            .header h1 {
                font-size: 2em;
            }
            
            .option-row {
                grid-template-columns: 1fr;
            }
            
            .download-options {
                flex-direction: column;
            }
            
            .download-btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">📱</div>
            <h1>QR Code Generator</h1>
            <p>Create stunning QR codes for free. Customize colors, download in multiple formats.</p>
        </div>

        <div class="main-content">
            <div class="input-section">
                <div class="tab-buttons">
                    <button class="tab-btn active" data-tab="url">🌐 URL</button>
                    <button class="tab-btn" data-tab="text">📝 Text</button>
                    <button class="tab-btn" data-tab="wifi">📶 WiFi</button>
                    <button class="tab-btn" data-tab="contact">👤 Contact</button>
                </div>

                <div class="input-group">
                    <label for="qrContent">Enter your content:</label>
                    <input type="text" class="url-input" id="qrContent" 
                           placeholder="https://example.com or any text..." value="https://www.google.com">
                </div>

                <div class="customization-options">
                    <h3 style="margin-bottom: 20px; color: #2c3e50;">🎨 Customize QR Code</h3>
                    
                    <div class="option-row">
                        <div class="color-picker">
                            <label>Foreground Color:</label>
                            <input type="color" id="fgColor" value="#000000">
                        </div>
                        <div class="color-picker">
                            <label>Background Color:</label>
                            <input type="color" id="bgColor" value="#ffffff">
                        </div>
                    </div>

                    <div class="option-row">
                        <div>
                            <label for="qrSize">Size:</label>
                            <select id="qrSize" class="url-input">
                                <option value="200">Small (200x200)</option>
                                <option value="300" selected>Medium (300x300)</option>
                                <option value="400">Large (400x400)</option>
                            </select>
                        </div>
                        <div>
                            <label for="qrMargin">Margin:</label>
                            <select id="qrMargin" class="url-input">
                                <option value="0">No margin</option>
                                <option value="1" selected>Small margin</option>
                                <option value="2">Large margin</option>
                            </select>
                        </div>
                    </div>
                </div>

                <button class="generate-btn" id="generateBtn">
                    🚀 Generate QR Code
                </button>
            </div>

            <div class="preview-section">
                <h3 style="color: #2c3e50; margin-bottom: 20px;">QR Code Preview</h3>
                
                <div class="loading" id="loading">
                    <div class="spinner"></div>
                    <p>Generating your QR code...</p>
                </div>

                <div class="qr-preview" id="qrPreview">
                    <div class="qr-placeholder" id="qrPlaceholder">
                        Your QR code will appear here
                    </div>
                    <div id="qrcode"></div>
                </div>

                <div class="download-options" id="downloadOptions" style="display: none;">
                    <button class="download-btn png" onclick="downloadQRCode('png')">
                        📥 Download PNG
                    </button>
                    <button class="download-btn svg" onclick="downloadQRCode('svg')">
                        📥 Download SVG
                    </button>
                </div>
            </div>
        </div>

        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <h3>Instant Generation</h3>
                <p>Create QR codes in seconds with our fast and reliable generator</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎨</div>
                <h3>Customizable</h3>
                <p>Choose colors, sizes, and margins to match your brand</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">💾</div>
                <h3>Multiple Formats</h3>
                <p>Download in PNG, SVG formats for all your needs</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔒</div>
                <h3>100% Free</h3>
                <p>No registration required. Generate unlimited QR codes</p>
            </div>
        </div>

        <div class="ad-section">
            <h3>🚀 Go Premium - Unlock Advanced Features!</h3>
            <p>Get custom logos, analytics tracking, batch generation, and more!</p>
            <button class="premium-btn">Upgrade to Premium - $4.99/month</button>
        </div>

        <div class="footer">
            <p>&copy; 2024 QRCodePro. All rights reserved. | Free QR Code Generator</p>
        </div>
    </div>

    <!-- QR Code Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script>
        let qrcode = null;
        let currentQRCodeData = '';

        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
        });

        function initializeApp() {
            setupEventListeners();
            setupTabSystem();
            // Auto-generate QR code on page load
            setTimeout(generateQRCode, 1000);
            console.log('QR Code Generator Ready!');
        }

        function setupEventListeners() {
            // Generate button
            document.getElementById('generateBtn').addEventListener('click', generateQRCode);
            
            // Enter key support
            document.getElementById('qrContent').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    generateQRCode();
                }
            });

            // Color change listeners
            document.getElementById('fgColor').addEventListener('change', function() {
                if (currentQRCodeData) {
                    generateQRCode();
                }
            });

            document.getElementById('bgColor').addEventListener('change', function() {
                if (currentQRCodeData) {
                    generateQRCode();
                }
            });
        }

        function setupTabSystem() {
            const tabButtons = document.querySelectorAll('.tab-btn');
            
            tabButtons.forEach(button => {
                button.addEventListener('click', function() {
                    // Remove active class from all buttons
                    tabButtons.forEach(btn => btn.classList.remove('active'));
                    // Add active class to clicked button
                    this.classList.add('active');
                    
                    // Update placeholder based on tab
                    const tab = this.getAttribute('data-tab');
                    updatePlaceholder(tab);
                });
            });
        }

        function updatePlaceholder(tab) {
            const input = document.getElementById('qrContent');
            const placeholders = {
                url: 'https://example.com',
                text: 'Enter any text or message...',
                wifi: 'WIFI:S:MyNetwork;T:WPA;P:Password;;',
                contact: 'Name, Phone, Email...'
            };
            
            input.placeholder = placeholders[tab] || 'Enter your content...';
        }

        function generateQRCode() {
            const qrContent = document.getElementById('qrContent').value.trim();
            const loading = document.getElementById('loading');
            const qrPreview = document.getElementById('qrPreview');
            const qrPlaceholder = document.getElementById('qrPlaceholder');
            const downloadOptions = document.getElementById('downloadOptions');
            const generateBtn = document.getElementById('generateBtn');

            if (!qrContent) {
                alert('Please enter some content for the QR code');
                return;
            }

            // Show loading, hide placeholder
            loading.style.display = 'block';
            qrPlaceholder.style.display = 'none';
            downloadOptions.style.display = 'none';
            generateBtn.disabled = true;
            generateBtn.textContent = 'Generating...';

            // Get customization options
            const fgColor = document.getElementById('fgColor').value;
            const bgColor = document.getElementById('bgColor').value;
            const size = parseInt(document.getElementById('qrSize').value);
            const margin = parseInt(document.getElementById('qrMargin').value);

            // Clear previous QR code
            const qrcodeDiv = document.getElementById('qrcode');
            qrcodeDiv.innerHTML = '';

            // Small delay for better UX
            setTimeout(() => {
                try {
                    // Destroy previous QR code instance
                    if (qrcode) {
                        qrcode.clear();
                    }

                    // Create new QR code
                    qrcode = new QRCode(qrcodeDiv, {
                        text: qrContent,
                        width: size,
                        height: size,
                        colorDark: fgColor,
                        colorLight: bgColor,
                        correctLevel: QRCode.CorrectLevel.Q,
                        margin: margin
                    });

                    // Store current data for re-generation
                    currentQRCodeData = qrContent;

                    // Hide loading, show download options
                    setTimeout(() => {
                        loading.style.display = 'none';
                        downloadOptions.style.display = 'flex';
                        generateBtn.disabled = false;
                        generateBtn.textContent = '🚀 Generate QR Code';
                        console.log('QR Code generated successfully');
                    }, 500);

                } catch (error) {
                    console.error('Error generating QR code:', error);
                    alert('Error generating QR code. Please try again.');
                    
                    // Show error state
                    qrPlaceholder.innerHTML = `
                        <div style="color: #e74c3c;">
                            <p>❌ Error generating QR code</p>
                            <button onclick="generateQRCode()" style="padding: 10px 20px; background: #3498db; color: white; border: none; border-radius: 5px; margin-top: 10px;">
                                Try Again
                            </button>
                        </div>
                    `;
                    qrPlaceholder.style.display = 'block';
                    loading.style.display = 'none';
                    generateBtn.disabled = false;
                    generateBtn.textContent = '🚀 Generate QR Code';
                }
            }, 500);
        }

        function downloadQRCode(format) {
            try {
                const qrcodeDiv = document.getElementById('qrcode');
                const canvas = qrcodeDiv.querySelector('canvas');
                
                if (!canvas) {
                    alert('Please generate a QR code first');
                    return;
                }

                if (format === 'png') {
                    // Download as PNG
                    const link = document.createElement('a');
                    link.download = `qrcode-${Date.now()}.png`;
                    link.href = canvas.toDataURL('image/png');
                    document.body.appendChild(link);
                    link.click();
                    document.body.removeChild(link);
                } else if (format === 'svg') {
                    // For SVG, we'll create a simple SVG representation
                    downloadAsSVG();
                }
                
                console.log(`QR Code downloaded as ${format.toUpperCase()}`);
                
            } catch (error) {
                console.error('Error downloading QR code:', error);
                alert('Error downloading QR code. Please try again.');
            }
        }

        function downloadAsSVG() {
            // Simple SVG implementation
            const canvas = document.getElementById('qrcode').querySelector('canvas');
            const ctx = canvas.getContext('2d');
            const imageData = ctx.getImageData(0, 0, canvas.width, canvas.height);
            const data = imageData.data;
            
            let svgContent = `<svg width="${canvas.width}" height="${canvas.height}" xmlns="http://www.w3.org/2000/svg">`;
            svgContent += `<rect width="100%" height="100%" fill="${document.getElementById('bgColor').value}"/>`;
            
            const cellSize = 1; // Adjust based on QR code density
            
            for (let y = 0; y < canvas.height; y += cellSize) {
                for (let x = 0; x < canvas.width; x += cellSize) {
                    const idx = (y * canvas.width + x) * 4;
                    if (data[idx] === 0) { // Black pixel
                        svgContent += `<rect x="${x}" y="${y}" width="${cellSize}" height="${cellSize}" fill="${document.getElementById('fgColor').value}"/>`;
                    }
                }
            }
            
            svgContent += '</svg>';
            
            const link = document.createElement('a');
            link.download = `qrcode-${Date.now()}.svg`;
            link.href = 'data:image/svg+xml;charset=utf-8,' + encodeURIComponent(svgContent);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }

        // Example content for testing
        console.log('Try these examples:');
        console.log('1. https://www.youtube.com');
        console.log('2. Welcome to my website!');
        console.log('3. WIFI:S:MyNetwork;T:WPA;P:MyPassword;;');
    </script>
</body>
</html>
