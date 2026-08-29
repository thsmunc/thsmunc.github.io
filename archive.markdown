---
layout: default
title: Archive
permalink: /archive/
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Archive</title>
    <style>
        /* Minimal styling focused only on the PDF viewer */
        .pdf-controls {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        gap: 10px;
        margin-bottom: 20px;
    }

    .pdf-controls label {
        font-weight: 600;
        color: #550000;
    }

    #pdf-select {
        min-width: 250px;
        padding: 8px 12px;
        border: 1px solid #ddd;
        border-radius: 4px;
    }
        
        .pdf-viewer-wrapper {
            width: 100%;
            height: 65vh;
            border: 1px solid #e0e0e0;
            border-radius: 4px;
            overflow: hidden;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            background: #f9f9f9;
        }
        
        #pdf-viewer {
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .pdf-fallback {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100%;
            color: #666;
            text-align: center;
            padding: 20px;
        }
        
        /* Responsive adjustments */
        @media (max-width: 768px) {
            .pdf-viewer-wrapper {
                height: 60vh;
            }
        }
    </style>
</head>
<body>
    <div class="pdf-container">
        <div class="pdf-controls">
            <label for="pdf-select">Please select the edition of Colophon you would like to view by using the dropdown menu below:</label>
            <select id="pdf-select">
                <option value="">Choose an Edition</option>
                <option value="/source/pdfs/Colophon_2023_Volume_57.pdf">Colophon 2023 Volume 57</option>
                <option value="/source/pdfs/Colophon_2024_Volume_58.pdf">Colophon 2024 Volume 58</option>
                <option value="/source/pdfs/Colophon_2025_Volume_59.pdf">Colophon 2025 Volume 59</option>
            </select>
        </div>
        
        <div class="pdf-viewer-wrapper">
            <iframe id="pdf-viewer" src="about:blank"></iframe>
            <div class="pdf-fallback" id="pdf-fallback">
                <p>Please select a PDF document from the dropdown menu above.</p>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const pdfSelect = document.getElementById('pdf-select');
            const pdfViewer = document.getElementById('pdf-viewer');
            const pdfFallback = document.getElementById('pdf-fallback');
            
            pdfSelect.addEventListener('change', function() {
                if (this.value) {
                    pdfViewer.src = this.value;
                    pdfFallback.style.display = 'none';
                } else {
                    pdfViewer.src = 'about:blank';
                    pdfFallback.style.display = 'flex';
                }
            });
        });
    </script>
</body>
</html>
