<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carrusel Interactivo para OVA</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            color: #333;
        }
        
        .container {
            max-width: 900px;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            padding: 30px;
        }
        
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 20px;
            font-size: 2.5rem;
        }
        
        .subtitle {
            text-align: center;
            color: #7f8c8d;
            margin-bottom: 40px;
            font-size: 1.2rem;
        }
        
        .carousel-container {
            position: relative;
            width: 100%;
            height: 400px;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }
        
        .carousel-slide {
            display: none;
            position: absolute;
            width: 100%;
            height: 100%;
            transition: opacity 0.8s ease;
            opacity: 0;
        }
        
        .carousel-slide.active {
            display: flex;
            opacity: 1;
        }
        
        .slide-content {
            display: flex;
            width: 100%;
            height: 100%;
        }
        
        .slide-image {
            flex: 1;
            background-size: cover;
            background-position: center;
            border-top-left-radius: 10px;
            border-bottom-left-radius: 10px;
        }
        
        .slide-text {
            flex: 1;
            padding: 30px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            background-color: #fff;
        }
        
        .slide-text h2 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 1.8rem;
        }
        
        .slide-text p {
            color: #7f8c8d;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .carousel-controls {
            display: flex;
            justify-content: center;
            margin-top: 25px;
        }
        
        .carousel-controls button {
            background-color: #3498db;
            color: white;
            border: none;
            padding: 12px 25px;
            margin: 0 10px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(52, 152, 219, 0.3);
        }
        
        .carousel-controls button:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(52, 152, 219, 0.4);
        }
        
        .carousel-indicators {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        
        .indicator {
            width: 12px;
            height: 12px;
            background-color: #bdc3c7;
            border-radius: 50%;
            margin: 0 8px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        
        .indicator.active {
            background-color: #3498db;
            transform: scale(1.3);
        }
        
        .autoplay-control {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
        }
        
        .autoplay-control label {
            margin-left: 10px;
            color: #2c3e50;
            cursor: pointer;
        }
        
        @media (max-width: 768px) {
            .slide-content {
                flex-direction: column;
            }
            
            .slide-image {
                height: 200px;
                border-top-right-radius: 10px;
                border-bottom-left-radius: 0;
            }
            
            .carousel-container {
                height: auto;
            }
            
            h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Carrusel Interactivo para OVA</h1>
        <p class="subtitle">Explora contenidos educativos de manera interactiva</p>
        
        <div class="carousel-container">
            <!-- Slide 1 -->
            <div class="carousel-slide active">
                <div class="slide-content">
                    <div class="slide-image" style="background-image: url('https://media.posterlounge.com/img/products/770000/767282/767282_poster.jpg')"></div>
                    <div class="slide-text">
                        <h2>Introducción al Tema</h2>
                        <p>Comprende los conceptos básicos y fundamentales que sentarán las bases para tu aprendizaje. Este módulo te introducirá a los principios esenciales.</p>
                        <p>Duración: 15 minutos</p>
                    </div>
                </div>
            </div>
            
            <!-- Slide 2 -->
            <div class="carousel-slide">
                <div class="slide-content">
                    <div class="slide-image" style="background-image: url('https://images.unsplash.com/photo-1501504905252-473c47e087f8?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80')"></div>
                    <div class="slide-text">
                        <h2>Desarrollo de Contenidos</h2>
                        <p>Profundiza en los aspectos más importantes del tema con ejemplos prácticos y casos de estudio que reforzarán tu comprensión.</p>
                        <p>Duración: 30 minutos</p>
                    </div>
                </div>
            </div>
            
            <!-- Slide 3 -->
            <div class="carousel-slide">
                <div class="slide-content">
                    <div class="slide-image" style="background-image: url('https://images.unsplash.com/photo-1559028012-481c04fa702d?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80')"></div>
                    <div class="slide-text">
                        <h2>Ejercicios Prácticos</h2>
                        <p>Aplica lo aprendido mediante ejercicios interactivos que te permitirán evaluar tu progreso y consolidar tus conocimientos.</p>
                        <p>Duración: 25 minutos</p>
                    </div>
                </div>
            </div>
            
            <!-- Slide 4 -->
            <div class="carousel-slide">
                <div class="slide-content">
                    <div class="slide-image" style="background-image: url('https://images.unsplash.com/photo-1560785496-3c9d27877182?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80')"></div>
                    <div class="slide-text">
                        <h2>Evaluación Final</h2>
                        <p>Pon a prueba todo lo aprendido con una evaluación que medirá tu comprensión del tema y te ayudará a identificar áreas de mejora.</p>
                        <p>Duración: 20 minutos</p>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="carousel-controls">
            <button id="prevBtn">Anterior</button>
            <button id="nextBtn">Siguiente</button>
        </div>
        
        <div class="carousel-indicators">
            <div class="indicator active" data-index="0"></div>
            <div class="indicator" data-index="1"></div>
            <div class="indicator" data-index="2"></div>
            <div class="indicator" data-index="3"></div>
        </div>
        
        <div class="autoplay-control">
            <input type="checkbox" id="autoplay">
            <label for="autoplay">Reproducción automática</label>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const slides = document.querySelectorAll('.carousel-slide');
            const indicators = document.querySelectorAll('.indicator');
            const prevBtn = document.getElementById('prevBtn');
            const nextBtn = document.getElementById('nextBtn');
            const autoplayCheckbox = document.getElementById('autoplay');
            
            let currentSlide = 0;
            let autoplayInterval;
            
            // Función para mostrar una slide específica
            function showSlide(index) {
                // Ocultar todas las slides
                slides.forEach(slide => {
                    slide.classList.remove('active');
                });
                
                // Quitar la clase active de todos los indicadores
                indicators.forEach(indicator => {
                    indicator.classList.remove('active');
                });
                
                // Mostrar la slide actual y actualizar el indicador
                slides[index].classList.add('active');
                indicators[index].classList.add('active');
                
                currentSlide = index;
            }
            
            // Función para avanzar a la siguiente slide
            function nextSlide() {
                let nextIndex = (currentSlide + 1) % slides.length;
                showSlide(nextIndex);
            }
            
            // Función para retroceder a la slide anterior
            function prevSlide() {
                let prevIndex = (currentSlide - 1 + slides.length) % slides.length;
                showSlide(prevIndex);
            }
            
            // Event listeners para los botones
            nextBtn.addEventListener('click', nextSlide);
            prevBtn.addEventListener('click', prevSlide);
            
            // Event listeners para los indicadores
            indicators.forEach(indicator => {
                indicator.addEventListener('click', function() {
                    let index = parseInt(this.getAttribute('data-index'));
                    showSlide(index);
                    resetAutoplay();
                });
            });
            
            // Función para iniciar la reproducción automática
            function startAutoplay() {
                autoplayInterval = setInterval(nextSlide, 5000); // Cambia cada 5 segundos
            }
            
            // Función para detener la reproducción automática
            function stopAutoplay() {
                clearInterval(autoplayInterval);
            }
            
            // Función para resetear la reproducción automática
            function resetAutoplay() {
                stopAutoplay();
                if (autoplayCheckbox.checked) {
                    startAutoplay();
                }
            }
            
            // Control de reproducción automática
            autoplayCheckbox.addEventListener('change', function() {
                if (this.checked) {
                    startAutoplay();
                } else {
                    stopAutoplay();
                }
            });
            
            // Iniciar autoplay al cargar la página
            startAutoplay();
            autoplayCheckbox.checked = true;
            
            // Pausar autoplay cuando el ratón está sobre el carrusel
            const carouselContainer = document.querySelector('.carousel-container');
            carouselContainer.addEventListener('mouseenter', stopAutoplay);
            carouselContainer.addEventListener('mouseleave', function() {
                if (autoplayCheckbox.checked) {
                    startAutoplay();
                }
            });
            
            // Soporte para teclado
            document.addEventListener('keydown', function(e) {
                if (e.key === 'ArrowRight') {
                    nextSlide();
                    resetAutoplay();
                } else if (e.key === 'ArrowLeft') {
                    prevSlide();
                    resetAutoplay();
                }
            });
        });
    </script>
</body>
</html>
