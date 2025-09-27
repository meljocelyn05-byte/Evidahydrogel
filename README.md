<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Evida Hydrogel - Solución Innovadora para la Escasez de Agua</title>
    
    <!-- Tailwind CSS CDN - Cargado directamente para simplificar -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Chart.js CDN para las gráficas del Dashboard -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <!-- Google Fonts: Inter para una tipografía moderna y legible -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Favicon en formato SVG para un ícono simple y escalable -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>💧</text></svg>">

    <!-- Estilos CSS personalizados para complementar Tailwind y definir animaciones -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth; /* Desplazamiento suave al hacer clic en enlaces de anclaje */
        }
        /* Estilo para el texto con degradado */
        .gradient-text {
            background: linear-gradient(90deg, #10B981, #059669); /* Verde esmeralda a verde oscuro */
            -webkit-background-clip: text; /* Recorta el fondo al contorno del texto */
            -webkit-text-fill-color: transparent; /* Hace el texto transparente para mostrar el fondo */
            background-clip: text;
            text-fill-color: transparent;
        }
        /* Contenedor de gráficas para Chart.js con altura definida */
        .chart-container {
            position: relative;
            height: 300px; /* Altura fija para consistencia */
            width: 100%;
        }
        /* Animación para los KPI cards (contadores) */
        @keyframes count-up {
            from { transform: translateY(15px); opacity: 0; } /* Empieza ligeramente abajo y transparente */
            to { transform: translateY(0); opacity: 1; } /* Termina en posición y opaco */
        }
        .kpi-card-animation {
            animation: count-up 0.8s ease-out forwards; /* Aplica la animación */
        }
        
        /* Animación general para secciones que aparecen al hacer scroll */
        .fade-in-section {
            opacity: 0; /* Inicialmente transparente */
            transform: translateY(20px); /* Ligeramente desplazado hacia abajo */
            transition: opacity 0.6s ease-out, transform 0.6s ease-out; /* Transición suave */
        }
        .fade-in-section.is-visible {
            opacity: 1; /* Se vuelve opaco */
            transform: translateY(0); /* Vuelve a su posición original */
        }
        /* Estilo para las respuestas del FAQ (acordeón) */
        .faq-answer {
            max-height: 0; /* Inicialmente oculto */
            overflow: hidden; /* Oculta el contenido desbordado */
            transition: max-height 0.5s ease-in-out; /* Transición para el efecto de acordeón */
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <!-- Sección del Encabezado (Header) -->
    <header class="bg-white shadow-md sticky top-0 z-50">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <!-- Logo y Nombre del Proyecto -->
            <a href="#" class="text-2xl font-bold text-emerald-600 flex items-center">
                <!-- Ícono de gota de agua -->
                <svg class="w-8 h-8 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v.01"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18.5A6.5 6.5 0 1112 5.5a6.5 6.5 0 010 13z"></path></svg>
                Evida<span class="font-light">Hydrogel</span>
            </a>
            <!-- Menú de Navegación para Escritorio -->
            <div class="hidden md:flex space-x-6 items-center">
                <a href="#beneficios" class="text-gray-600 hover:text-emerald-600 transition duration-300">Beneficios</a>
                <a href="#como-funciona" class="text-gray-600 hover:text-emerald-600 transition duration-300">Cómo Funciona</a>
                <a href="#dashboard" class="text-gray-600 hover:text-emerald-600 transition duration-300">Impacto</a>
                <a href="#productos" class="text-gray-600 hover:text-emerald-600 transition duration-300">Productos</a>
                <a href="#faq" class="text-gray-600 hover:text-emerald-600 transition duration-300">FAQ</a>
                <a href="#contacto" class="bg-emerald-600 text-white px-4 py-2 rounded-full hover:bg-emerald-700 transition duration-300 shadow-lg">Contactar</a>
            </div>
            <!-- Botón de Menú para Móviles -->
            <button id="mobile-menu-button" class="md:hidden text-gray-700 focus:outline-none">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
        </nav>
        <!-- Menú Móvil Desplegable (inicialmente oculto) -->
        <div id="mobile-menu" class="hidden md:hidden">
            <a href="#beneficios" class="block py-2 px-4 text-sm hover:bg-gray-100">Beneficios</a>
            <a href="#como-funciona" class="block py-2 px-4 text-sm hover:bg-gray-100">Cómo Funciona</a>
            <a href="#dashboard" class="block py-2 px-4 text-sm hover:bg-gray-100">Impacto</a>
            <a href="#productos" class="block py-2 px-4 text-sm hover:bg-gray-100">Productos</a>
             <a href="#faq" class="block py-2 px-4 text-sm hover:bg-gray-100">FAQ</a>
            <a href="#contacto" class="block py-2 px-4 text-sm hover:bg-gray-100">Contactar</a>
        </div>
    </header>

    <!-- Contenido Principal de la Página -->
    <main>
        <!-- Sección Hero - Banner principal -->
        <section class="bg-white">
            <div class="container mx-auto px-6 py-20 md:py-32 grid md:grid-cols-2 gap-12 items-center">
                <!-- Texto Principal y Llamadas a la Acción -->
                <div class="text-center md:text-left fade-in-section is-visible">
                    <h1 class="text-4xl md:text-6xl font-extrabold text-gray-900 leading-tight">
                        Transforma la Sequía en 
                        <span class="gradient-text">Abundancia</span>
                    </h1>
                    <p class="mt-6 text-lg text-gray-600 max-w-xl mx-auto md:mx-0">
                        Conoce Evida Hydrogel, el poliacrilato de potasio que retiene hasta 500 veces su peso en agua, revolucionando la agricultura y garantizando el futuro de tus cultivos.
                    </p>
                    <div class="mt-8 flex justify-center md:justify-start space-x-4">
                        <a href="#productos" class="bg-emerald-600 text-white px-8 py-3 rounded-full text-lg font-semibold hover:bg-emerald-700 transition duration-300 shadow-xl transform hover:scale-105">Comprar Ahora</a>
                        <a href="#dashboard" class="bg-gray-200 text-gray-800 px-8 py-3 rounded-full text-lg font-semibold hover:bg-gray-300 transition duration-300">Ver Impacto</a>
                    </div>
                </div>
                <!-- Imagen principal de la sección hero -->
                <div class="hidden md:block fade-in-section is-visible" style="transition-delay: 200ms;">
                    <img src="https://images.unsplash.com/photo-1625246333195-78d9c38ad449?q=80&w=2070&auto=format&fit=crop" alt="Manos de agricultor sosteniendo tierra fértil con un brote verde" class="rounded-2xl shadow-2xl object-cover w-full h-full">
                </div>
            </div>
        </section>

        <!-- Sección de Beneficios -->
        <section id="beneficios" class="py-20 fade-in-section">
            <div class="container mx-auto px-6">
                 <div class="text-center mb-12">
                    <h2 class="text-4xl font-bold text-gray-900">Agricultura Inteligente y Sostenible</h2>
                    <p class="mt-4 text-lg text-gray-600">Maximiza tus resultados con menos recursos.</p>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Tarjeta de Beneficio 1: Súper Absorción -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Súper Absorción</h3>
                        <p class="text-gray-600">Retiene hasta 500 veces su peso en agua, liberándola gradualmente.</p>
                    </div>
                     <!-- Tarjeta de Beneficio 2: 100% Seguro -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">100% Seguro</h3>
                        <p class="text-gray-600">Producto no tóxico, seguro para cultivos, suelo y medio ambiente.</p>
                    </div>
                     <!-- Tarjeta de Beneficio 3: Ecológico -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Ecológico</h3>
                        <p class="text-gray-600">Biodegradable, se descompone de forma natural sin dejar residuos.</p>
                    </div>
                     <!-- Tarjeta de Beneficio 4: Aumenta Productividad -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Aumenta Productividad</h3>
                        <p class="text-gray-600">Mejora el crecimiento y aumenta el rendimiento de la cosecha.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección "Cómo Funciona" -->
        <section id="como-funciona" class="py-20 bg-white fade-in-section">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-4xl font-bold text-gray-900">La Ciencia Detrás de Cada Gota</h2>
                    <p class="mt-4 text-lg text-gray-600 max-w-3xl mx-auto">Nuestro hidrogel actúa como un reservorio de agua inteligente directamente en la raíz de tus plantas. Así es como funciona:</p>
                </div>
                <div class="grid md:grid-cols-3 gap-8 text-center">
                    <!-- Paso 1: Absorción Rápida -->
                    <div class="p-6">
                        <img src="https://placehold.co/300x200/d1fae5/059669?text=Paso+1" alt="Absorción de agua" class="rounded-xl shadow-lg mx-auto mb-6">
                        <h3 class="text-2xl font-bold mb-2">1. Absorción Rápida</h3>
                        <p class="text-gray-600">Al contacto con el agua de lluvia o riego, los gránulos de Evida se expanden y la absorben, convirtiéndola en un gel nutritivo.</p>
                    </div>
                    <!-- Paso 2: Almacenamiento Eficiente -->
                     <div class="p-6">
                        <img src="https://placehold.co/300x200/a7f3d0/059669?text=Paso+2" alt="Almacenamiento de agua" class="rounded-xl shadow-lg mx-auto mb-6">
                        <h3 class="text-2xl font-bold mb-2">2. Almacenamiento Eficiente</h3>
                        <p class="text-gray-600">El gel retiene el agua en la zona radicular, evitando la evaporación y el escurrimiento, manteniéndola disponible por más tiempo.</p>
                    </div>
                    <!-- Paso 3: Liberación Inteligente -->
                     <div class="p-6">
                        <img src="https://placehold.co/300x200/6ee7b7/059669?text=Paso+3" alt="Liberación de agua" class="rounded-xl shadow-lg mx-auto mb-6">
                        <h3 class="text-2xl font-bold mb-2">3. Liberación Inteligente</h3>
                        <p class="text-gray-600">Cuando el suelo se seca, las raíces absorben la humedad del gel según su necesidad, asegurando una hidratación constante.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección de Dashboard de Impacto -->
        <section id="dashboard" class="py-20 fade-in-section">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900">Dashboard de Impacto Social y Agrícola</h2>
                    <p class="mt-4 text-lg text-gray-600">Resultados comprobados que demuestran la eficacia de Evida Hydrogel.</p>
                </div>

                <!-- KPIs (Indicadores Clave de Desempeño) -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 mb-16 text-center">
                    <div class="bg-white p-6 rounded-2xl shadow-lg kpi-card-animation">
                        <p class="text-5xl font-extrabold gradient-text">30-70%</p>
                        <p class="mt-2 text-gray-700 font-semibold">Reducción de Riego</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-lg kpi-card-animation" style="animation-delay: 0.2s;">
                        <p class="text-5xl font-extrabold gradient-text">+65%</p>
                        <p class="mt-2 text-gray-700 font-semibold">Incremento en Rendimiento</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-lg kpi-card-animation" style="animation-delay: 0.4s;">
                        <p class="text-5xl font-extrabold gradient-text">+90%</p>
                        <p class="mt-2 text-gray-700 font-semibold">Tasa de Supervivencia</p>
                    </div>
                </div>

                <!-- Gráficas y Mapa de Impacto -->
                <div class="grid grid-cols-1 lg:grid-cols-5 gap-8">
                    <!-- Contenedor para las Gráficas principales -->
                    <div class="lg:col-span-3 grid grid-cols-1 md:grid-cols-2 gap-8">
                        <div class="bg-white p-6 rounded-2xl shadow-lg">
                            <h3 class="font-bold text-lg mb-4 text-center">Ahorro de Agua con Evida</h3>
                            <div class="chart-container">
                                <canvas id="ahorroAguaChart"></canvas>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-2xl shadow-lg">
                            <h3 class="font-bold text-lg mb-4 text-center">Impacto en Productividad</h3>
                             <div class="chart-container">
                                <canvas id="productividadChart"></canvas>
                            </div>
                        </div>
                        <div class="md:col-span-2 bg-white p-6 rounded-2xl shadow-lg">
                            <h3 class="font-bold text-lg mb-4 text-center">Eficiencia en Uso de Fertilizantes</h3>
                            <div class="chart-container">
                                <canvas id="nutrientesChart"></canvas>
                            </div>
                        </div>
                    </div>

                    <!-- Mapa interactivo de México -->
                    <div class="lg:col-span-2 bg-white p-6 rounded-2xl shadow-lg">
                        <h3 class="font-bold text-lg mb-4 text-center">Nuestro Impacto en México</h3>
                        <p class="text-center text-sm text-gray-500 mb-4">Zonas con estrés hídrico donde nuestra solución tiene mayor potencial.</p>
                        <!-- SVG del mapa de México. Los estados con `fill="#10B981"` (verde esmeralda) representan zonas de mayor impacto o estrés hídrico. -->
                        <svg viewBox="0 0 1039 692" xmlns="http://www.w3.org/2000/svg" class="w-full h-auto">
                           <path d="M112.5 137.5L108 141L101 135L102 129L108.5 120.5L115 122L120 128.5L112.5 137.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Baja-California-Sur"></path>
                            <path d="M120 128.5L115 122L108.5 120.5L110.5 106L120.5 81L130.5 61.5L138 48L148 40.5L155 35.5L157 30L160.5 31L163 42L159 52.5L153 62.5L151 76.5L142 97L138.5 110L135 119L120 128.5Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="Baja-California"></path>
                            <path d="M160.5 31L167 36L182.5 50L193.5 60.5L204 74L213.5 84L225.5 101.5L230 115.5L230.5 128L218 139L208 141L196.5 145.5L194.5 152L188 153L184.5 159L180 158L166 142.5L163 131.5L163.5 119.5L166.5 105L169.5 89.5L167 71L163 56L163 42L160.5 31Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="Sonora"></path>
                            <path d="M230.5 128L230 115.5L241 120L249.5 132L253 142L253.5 152L249 161.5L241.5 171.5L241.5 180.5L232.5 182L224 176.5L218 168.5L216.5 159.5L218 139L230.5 128Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Sinaloa"></path>
                            <path d="M253.5 152L253 142L249.5 132L241 120L230 115.5L225.5 101.5L242.5 102L261.5 112L282.5 123.5L299 133.5L317.5 145.5L327 159L319.5 169.5L309 173L296.5 178.5L286.5 186.5L280 196L272.5 202L261 204.5L251.5 198L241.5 180.5L241.5 171.5L249 161.5L253.5 152Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="Chihuahua"></path>
                            <path d="M251.5 198L261 204.5L272.5 202L280 196L286.5 186.5L296.5 178.5L309 173L319.5 169.5L327 159L343.5 171L351.5 184L355 201L343 214L328 222.5L313 226.5L302.5 231L292 233.5L281 229L265.5 217L251.5 198Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="Durango"></path>
                            <path d="M327 159L317.5 145.5L322.5 139.5L332.5 134L342 133L351 138L360 148L370 152.5L381.5 162.5L383 172.5L369.5 178L351.5 184L343.5 171L327 159Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="Coahuila"></path>
                            <path d="M281 229L292 233.5L302.5 231L313 226.5L320.5 231.5L327 240.5L324.5 249.5L317.5 254.5L306.5 255.5L294.5 252L286 244L281 229Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Zacatecas"></path>
                            <path d="M286 244L294.5 252L306.5 255.5L317.5 254.5L324.5 249.5L327 240.5L320.5 231.5L328 222.5L343 214L355 201L351.5 184L369.5 178L383 172.5L381.5 162.5L392 168.5L402 178.5L412 185L421 199.5L430.5 212L431.5 221L424.5 229.5L414 235L400.5 244.5L388 253.5L380 260.5L369 265.5L361.5 272L351 274.5L341 270.5L331.5 264L323 264.5L309 260L295 256.5L286 244Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="Nuevo-Leon"></path>
                            <path d="M265.5 217L281 229L286 244L281 254.5L273 260L264.5 264L259 261.5L254.5 253.5L254 245L258 238L265.5 228.5L265.5 217Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Nayarit"></path>
                            <path d="M431.5 221L430.5 212L438 214.5L449.5 220L458.5 230L464 240.5L462.5 249.5L453.5 252.5L444 252.5L434.5 248.5L424.5 229.5L431.5 221Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Tamaulipas"></path>
                            <path d="M309 260L323 264.5L331.5 264L341 270.5L351 274.5L361.5 272L369 265.5L380 260.5L388 253.5L400.5 244.5L414 235L424.5 229.5L434.5 248.5L444 252.5L453.5 252.5L462.5 249.5L464 240.5L471.5 251.5L474 262.5L469 270.5L456.5 277L444.5 281L432 284.5L422.5 290.5L412.5 292.5L401.5 288.5L389.5 281.5L378 276.5L365.5 276L350 280L336.5 285L324.5 285L309 277.5L309 260Z" fill="#10B981" stroke="#059669" stroke-width="1.5" class="hover:fill-emerald-600 transition-colors duration-300" id="San-Luis-Potosi"></path>
                            <path d="M281 254.5L286 244L295 256.5L309 260L309 277.5L296.5 278.5L284 271.5L281 254.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Aguascalientes"></path>
                            <path d="M284 271.5L296.5 278.5L309 277.5L324.5 285L336.5 285L350 280L350.5 288L343 297L330.5 301.5L323 306.5L311.5 306L300 299.5L287.5 289L284 271.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Jalisco"></path>
                            <path d="M365.5 276L378 276.5L389.5 281.5L401.5 288.5L407 295.5L402 301.5L392.5 303.5L382 301L371 295.5L360.5 291.5L350.5 288L350 280L365.5 276Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Guanajuato"></path>
                            <path d="M300 299.5L311.5 306L323 306.5L318 316.5L306.5 320L296 313.5L290.5 305L300 299.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Colima"></path>
                            <path d="M382 301L392.5 303.5L402 301.5L407 295.5L412.5 292.5L422.5 290.5L426.5 296L423 302L413.5 306.5L402.5 309.5L392.5 311L382 301Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Queretaro"></path>
                            <path d="M330.5 301.5L343 297L350.5 288L360.5 291.5L371 295.5L382 301L392.5 311L402.5 309.5L413.5 306.5L423 302L426.5 296L432 284.5L444.5 281L456.5 277L469 270.5L474 262.5L480 268L487.5 278.5L487.5 288.5L481 296.5L474 301L465.5 305L456.5 306.5L448 309.5L440.5 315.5L431.5 321L425.5 328.5L429 336.5L438 340.5L428.5 347.5L419 347L409 341.5L400 335.5L389 331.5L377.5 330.5L366.5 326.5L356.5 326.5L346 321.5L337 318L323 322.5L318 316.5L323 306.5L330.5 301.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Michoacan"></path>
                            <path d="M425.5 328.5L431.5 321L440.5 315.5L448 309.5L456.5 306.5L465.5 305L474 301L481 296.5L487.5 288.5L495 294.5L500.5 301.5L503.5 310L503.5 319.5L498 325.5L489 328.5L480.5 332.5L471.5 335L461.5 335.5L452 332.5L442.5 331L435.5 330L425.5 328.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Mexico"></path>
                            <path d="M487.5 288.5L487.5 278.5L494 284L495 294.5L487.5 288.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Tlaxcala"></path>
                            <path d="M422.5 290.5L412.5 292.5L407 295.5L392.5 303.5L392.5 311L402.5 309.5L413.5 306.5L423 302L426.5 296L422.5 290.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Hidalgo"></path>
                            <path d="M435.5 330L442.5 331L452 332.5L461.5 335.5L466.5 340L462.5 346.5L454 348L445.5 345L438 340.5L435.5 330Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Morelos"></path>
                            <path d="M461.5 335.5L471.5 335L480.5 332.5L489 328.5L498 325.5L503.5 319.5L503.5 310L500.5 301.5L495 294.5L494 284L487.5 278.5L480 268L474 262.5L482 260.5L491.5 264.5L501 271.5L511 280.5L519 291.5L523.5 302.5L523.5 312L518 319.5L509.5 324L500.5 329L491 333L482.5 338L474.5 342L466.5 340L461.5 335.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Puebla"></path>
                            <path d="M511 280.5L501 271.5L491.5 264.5L482 260.5L474 262.5L471.5 251.5L464 240.5L462.5 249.5L464 256.5L470 264.5L480 268L487.5 278.5L494 284L503.5 292.5L513.5 300L523.5 302.5L533.5 302.5L543 299L552.5 292L559 283.5L560.5 274.5L555.5 267.5L546.5 263.5L536.5 263.5L526.5 267.5L518.5 272.5L511 280.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Veracruz"></path>
                            <path d="M377.5 330.5L389 331.5L400 335.5L409 341.5L419 347L428.5 347.5L438 340.5L445.5 345L454 348L462.5 346.5L466.5 340L474.5 342L482.5 338L491 333L500.5 329L509.5 324L518 319.5L523.5 312L529 319L535 327.5L535.5 338.5L529.5 346.5L520 351L509.5 354L499 355L488 352.5L477 348.5L466.5 347.5L456 349.5L445.5 354.5L435 357.5L424.5 359.5L414 358.5L404 354.5L393.5 351L383 344L377.5 330.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Guerrero"></path>
                            <path d="M523.5 312L523.5 302.5L519 291.5L526 295.5L535 307.5L535 318L529 319L523.5 312Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Oaxaca-part-1"></path>
                            <path d="M535 327.5L529 319L535 307.5L526 295.5L519 291.5L511 280.5L518.5 272.5L526.5 267.5L536.5 263.5L546.5 263.5L555.5 267.5L560.5 274.5L566 280.5L572 289L575.5 299.5L575 310L569.5 317.5L561.5 322.5L552 325L543.5 325.5L535 327.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Oaxaca-part-2"></path>
                            <path d="M552.5 292L543 299L533.5 302.5L523.5 302.5L526 295.5L535.5 289L545.5 284.5L552.5 292Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Oaxaca-part-3"></path>
                            <path d="M575.5 299.5L572 289L566 280.5L560.5 274.5L559 283.5L563.5 291.5L570.5 299.5L575.5 299.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Chiapas-part-1"></path>
                            <path d="M552 325L561.5 322.5L569.5 317.5L575 310L570.5 299.5L563.5 291.5L559 283.5L552.5 292L556 299.5L557 308.5L552 316.5L552 325Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Chiapas-part-2"></path>
                            <path d="M560.5 274.5L555.5 267.5L560 261L568 258L577.5 258.5L587 263.5L594 270L597 278.5L594.5 285.5L587.5 289.5L579.5 289.5L572 289L566 280.5L560.5 274.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Tabasco"></path>
                            <path d="M594.5 285.5L597 278.5L603.5 282.5L608 289L608 297.5L603 303.5L596 304.5L589 300.5L587.5 289.5L594.5 285.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Campeche"></path>
                            <path d="M608 289L603.5 282.5L597 278.5L594 270L597 263.5L603 259.5L611.5 259.5L619.5 264.5L625 271.5L626.5 280L622.5 287.5L615 291.5L608 289Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Yucatan"></path>
                            <path d="M622.5 287.5L626.5 280L625 271.5L628 268L634.5 268.5L641 273L644.5 279L645 286.5L641.5 292.5L635 295.5L628.5 293L622.5 287.5Z" fill="#a7f3d0" stroke="#10B981" stroke-width="1.5" class="hover:fill-emerald-500 transition-colors duration-300" id="Quintana-Roo"></path>
                            <text x="450" y="320" font-family="Inter, sans-serif" font-size="12" fill="#6B7280" text-anchor="middle">CDMX</text>
                        </svg>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección de Productos -->
        <section id="productos" class="py-20 bg-white fade-in-section">
            <div class="container mx-auto px-6">
                 <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900">Nuestro Catálogo de Productos</h2>
                    <p class="mt-4 text-lg text-gray-600">Soluciones de hidrogel para cada necesidad agrícola.</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Tarjeta de Producto 1: Evida Agro Premium -->
                    <div class="bg-white rounded-2xl shadow-lg overflow-hidden group">
                        <img src="https://images.unsplash.com/photo-1598379434222-1775b6a78846?q=80&w=1964&auto=format&fit=crop" alt="Poliacrilato Agrícola" class="w-full h-56 object-cover group-hover:scale-105 transition-transform duration-300">
                        <div class="p-6">
                            <h3 class="text-xl font-bold mb-2">Evida Agro Premium</h3>
                            <p class="text-gray-600 mb-4">Formulado para máxima retención hídrica en todo tipo de cultivos. Ideal para agricultura extensiva.</p>
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-bold text-emerald-600">$850 <span class="text-sm font-normal text-gray-500">/ 25kg</span></span>
                                <button class="bg-emerald-100 text-emerald-800 px-4 py-2 rounded-full font-semibold hover:bg-emerald-200 transition duration-300">Agregar</button>
                            </div>
                        </div>
                    </div>
                    <!-- Tarjeta de Producto 2: Evida Bio Sostenible -->
                    <div class="bg-white rounded-2xl shadow-lg overflow-hidden group">
                        <img src="https://images.unsplash.com/photo-1581458233322-20e3a6a43924?q=80&w=1964&auto=format&fit=crop" alt="Poliacrilato Biodegradable" class="w-full h-56 object-cover group-hover:scale-105 transition-transform duration-300">
                        <div class="p-6">
                            <h3 class="text-xl font-bold mb-2">Evida Bio Sostenible</h3>
                            <p class="text-gray-600 mb-4">Nuestra fórmula ecológica y biodegradable. Perfecta para reforestación y jardinería sustentable.</p>
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-bold text-emerald-600">$1100 <span class="text-sm font-normal text-gray-500">/ 20kg</span></span>
                                <button class="bg-emerald-100 text-emerald-800 px-4 py-2 rounded-full font-semibold hover:bg-emerald-200 transition duration-300">Agregar</button>
                            </div>
                        </div>
                    </div>
                    <!-- Tarjeta de Producto 3: Evida Micro Jardinería -->
                    <div class="bg-white rounded-2xl shadow-lg overflow-hidden group">
                        <img src="https://images.unsplash.com/photo-1605469041208-54a852a489c4?q=80&w=1974&auto=format&fit=crop" alt="Poliacrilato Micronizado para viveros" class="w-full h-56 object-cover group-hover:scale-105 transition-transform duration-300">
                        <div class="p-6">
                            <h3 class="text-xl font-bold mb-2">Evida Micro Jardinería</h3>
                            <p class="text-gray-600 mb-4">Granulometría fina para viveros, semilleros y jardinería de precisión. Rápida absorción y fácil aplicación.</p>
                            <div class="flex justify-between items-center">
                                <span class="text-2xl font-bold text-emerald-600">$250 <span class="text-sm font-normal text-gray-500">/ 500g</span></span>
                                <button class="bg-emerald-100 text-emerald-800 px-4 py-2 rounded-full font-semibold hover:bg-emerald-200 transition duration-300">Agregar</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección de Testimonios -->
        <section class="py-20 bg-emerald-50 fade-in-section">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-4xl font-bold text-gray-900">Lo que Dicen Nuestros Clientes</h2>
                    <p class="mt-4 text-lg text-gray-600">Historias de éxito de agricultores como tú.</p>
                </div>
                <div class="grid md:grid-cols-2 gap-8">
                    <!-- Testimonio 1 -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg flex flex-col sm:flex-row items-center gap-6">
                        <img class="w-24 h-24 rounded-full object-cover" src="https://images.unsplash.com/photo-1560787313-5dff3307e257?q=80&w=1964&auto=format&fit=crop" alt="Foto de cliente satisfecho" loading="lazy">
                        <div>
                            <p class="text-gray-600 italic">"Desde que uso Evida, reduje mis ciclos de riego a la mitad y mis cosechas de maíz nunca habían sido tan abundantes. Es una inversión que se paga sola."</p>
                            <p class="mt-4 font-bold text-emerald-700">- Carlos R., Agricultor en Sinaloa</p>
                        </div>
                    </div>
                    <!-- Testimonio 2 -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg flex flex-col sm:flex-row items-center gap-6">
                        <img class="w-24 h-24 rounded-full object-cover" src="https://images.unsplash.com/photo-1599485659222-282f9ba3dc85?q=80&w=1964&auto=format&fit=crop" alt="Foto de clienta satisfecha" loading="lazy">
                        <div>
                            <p class="text-gray-600 italic">"En mi vivero, la supervivencia de los plantones es crucial. Con Evida Hydrogel, la tasa de éxito es casi del 100%. ¡Mis clientes están encantados!"</p>
                            <p class="mt-4 font-bold text-emerald-700">- Sofía G., Propietaria de Vivero en Jalisco</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Sección de Preguntas Frecuentes (FAQ) -->
        <section id="faq" class="py-20 bg-white fade-in-section">
            <div class="container mx-auto px-6 max-w-4xl">
                 <div class="text-center mb-12">
                    <h2 class="text-4xl font-bold text-gray-900">Preguntas Frecuentes</h2>
                    <p class="mt-4 text-lg text-gray-600">Resolvemos tus dudas más comunes.</p>
                </div>
                <div class="space-y-4">
                    <!-- Pregunta FAQ 1 -->
                    <div class="bg-gray-50 rounded-lg">
                        <button class="faq-question w-full flex justify-between items-center text-left p-6 font-semibold text-lg focus:outline-none">
                            <span>¿El hidrogel es tóxico o daña el medio ambiente?</span>
                            <svg class="w-6 h-6 transform transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                        <div class="faq-answer px-6 pb-6 text-gray-600">
                            <p>No, nuestro producto es 100% seguro y no tóxico. Está diseñado para ser biodegradable, descomponiéndose de forma natural en el suelo sin dejar residuos perjudiciales, lo que lo hace una opción completamente sostenible.</p>
                        </div>
                    </div>
                     <!-- Pregunta FAQ 2 -->
                    <div class="bg-gray-50 rounded-lg">
                        <button class="faq-question w-full flex justify-between items-center text-left p-6 font-semibold text-lg focus:outline-none">
                            <span>¿Cuánto tiempo dura el producto en el suelo?</span>
                            <svg class="w-6 h-6 transform transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                        <div class="faq-answer px-6 pb-6 text-gray-600">
                            <p>La efectividad de Evida Hydrogel puede durar entre 3 y 5 años en el suelo, dependiendo de las condiciones climáticas y el tipo de terreno. Durante este tiempo, seguirá absorbiendo y liberando agua en múltiples ciclos.</p>
                        </div>
                    </div>
                     <!-- Pregunta FAQ 3 -->
                    <div class="bg-gray-50 rounded-lg">
                        <button class="faq-question w-full flex justify-between items-center text-left p-6 font-semibold text-lg focus:outline-none">
                            <span>¿Cómo sé qué cantidad de producto necesito?</span>
                            <svg class="w-6 h-6 transform transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                        <div class="faq-answer px-6 pb-6 text-gray-600">
                            <p>La dosis recomendada varía según el tipo de cultivo, la composición del suelo y el clima. Nuestra plataforma digital y nuestro equipo de soporte técnico pueden brindarte una recomendación personalizada para asegurar los mejores resultados.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección de Contacto -->
        <section id="contacto" class="py-20 bg-emerald-700 text-white fade-in-section">
            <div class="container mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
                <!-- Información de Contacto -->
                <div>
                    <h2 class="text-4xl font-bold">¿Listo para transformar tu cultivo?</h2>
                    <p class="mt-4 text-emerald-200 text-lg">Nuestro equipo de especialistas está aquí para ayudarte. Contáctanos para recibir una cotización personalizada o asesoría técnica gratuita.</p>
                    <div class="mt-8 space-y-4">
                        <p class="flex items-center text-lg"><svg class="w-5 h-5 mr-3 text-emerald-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg> ventas@evida.com</p>
                        <p class="flex items-center text-lg"><svg class="w-5 h-5 mr-3 text-emerald-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg> +52 (55) 1234-5678</p>
                        <p class="flex items-center text-lg"><svg class="w-5 h-5 mr-3 text-emerald-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg> Durango, Dgo. México</p>
                    </div>
                </div>
                <!-- Formulario de Contacto -->
                <div class="bg-white p-8 rounded-2xl shadow-2xl">
                    <form action="#" method="POST">
                        <div class="space-y-6">
                            <div>
                                <label for="full-name" class="text-sm font-semibold text-gray-700">Nombre completo</label>
                                <input type="text" id="full-name" class="mt-1 block w-full px-4 py-2 bg-gray-100 border border-gray-200 rounded-md focus:ring-emerald-500 focus:border-emerald-500 text-gray-800" required>
                            </div>
                             <div>
                                <label for="email" class="text-sm font-semibold text-gray-700">Email</label>
                                <input type="email" id="email" class="mt-1 block w-full px-4 py-2 bg-gray-100 border border-gray-200 rounded-md focus:ring-emerald-500 focus:border-emerald-500 text-gray-800" required>
                            </div>
                            <div>
                                <label for="project" class="text-sm font-semibold text-gray-700">Cuéntanos sobre tu proyecto</label>
                                <textarea id="project" rows="4" class="mt-1 block w-full px-4 py-2 bg-gray-100 border border-gray-200 rounded-md focus:ring-emerald-500 focus:border-emerald-500 text-gray-800" required></textarea>
                            </div>
                            <div>
                                <button type="submit" class="w-full bg-emerald-600 text-white px-6 py-3 rounded-md text-lg font-semibold hover:bg-emerald-700 transition duration-300 shadow-lg transform hover:scale-105">Enviar Consulta</button>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- Sección del Pie de Página (Footer) -->
    <footer class="bg-gray-900 text-white">
        <div class="container mx-auto px-6 py-12">
             <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
                <!-- Información del Proyecto -->
                <div>
                    <h3 class="text-lg font-bold">Evida Hydrogel</h3>
                    <p class="mt-2 text-gray-400 text-sm">Innovación para un futuro agrícola sostenible y resiliente.</p>
                </div>
                 <!-- Enlaces de Productos -->
                 <div>
                    <h4 class="font-semibold">Productos</h4>
                    <ul class="mt-4 space-y-2 text-sm">
                        <li><a href="#productos" class="text-gray-400 hover:text-white">Evida Agro Premium</a></li>
                        <li><a href="#productos" class="text-gray-400 hover:text-white">Evida Bio Sostenible</a></li>
                        <li><a href="#productos" class="text-gray-400 hover:text-white">Evida Micro Jardinería</a></li>
                    </ul>
                </div>
                 <!-- Enlaces de Navegación Rápida -->
                 <div>
                    <h4 class="font-semibold">Navegación</h4>
                    <ul class="mt-4 space-y-2 text-sm">
                        <li><a href="#como-funciona" class="text-gray-400 hover:text-white">Cómo Funciona</a></li>
                        <li><a href="#dashboard" class="text-gray-400 hover:text-white">Impacto</a></li>
                        <li><a href="#faq" class="text-gray-400 hover:text-white">Preguntas Frecuentes</a></li>
                    </ul>
                </div>
                <!-- Información de Contacto en el Footer -->
                <div>
                    <h4 class="font-semibold">Contacto</h4>
                     <ul class="mt-4 space-y-2 text-sm text-gray-400">
                        <li>ventas@evida.com</li>
                        <li>+52 (55) 1234-5678</li>
                        <li>Durango, México</li>
                    </ul>
                </div>
             </div>
             <!-- Derechos de Autor y Año -->
             <div class="mt-12 border-t border-gray-800 pt-8 text-center text-sm text-gray-500">
                <p>&copy; 2025 Evida. Todos los derechos reservados. Proyecto de Transformación Digital - Tecmilenio.</p>
             </div>
        </div>
    </footer>

    <!-- Script JavaScript para interactividad (menú móvil, animaciones, gráficas) -->
    <script>
        // Lógica para el menú móvil: alterna la visibilidad al hacer clic en el botón
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');
        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Lógica para animaciones al hacer scroll (fade-in para secciones)
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible'); // Añade la clase para hacer visible la sección
                }
            });
        }, {
            threshold: 0.1 /* Un 10% de la sección debe ser visible para activar la animación */
        });

        // Observa todas las secciones con la clase 'fade-in-section'
        document.querySelectorAll('.fade-in-section').forEach(section => {
            observer.observe(section);
        });

        // Lógica para el acordeón de Preguntas Frecuentes (FAQ)
        const faqQuestions = document.querySelectorAll('.faq-question');
        faqQuestions.forEach(question => {
            question.addEventListener('click', () => {
                const answer = question.nextElementSibling; // La respuesta es el siguiente elemento hermano
                const icon = question.querySelector('svg'); // El ícono para girar

                // Cierra otras respuestas abiertas antes de abrir la actual
                question.parentElement.parentElement.querySelectorAll('.faq-answer').forEach(ans => {
                    if (ans !== answer && ans.style.maxHeight) {
                        ans.style.maxHeight = null;
                        ans.previousElementSibling.querySelector('svg').classList.remove('rotate-180');
                    }
                });
                
                // Abre o cierra la respuesta actual
                if (answer.style.maxHeight) {
                    answer.style.maxHeight = null; /* Cierra la respuesta */
                    icon.classList.remove('rotate-180'); /* Gira el ícono a su posición original */
                } else {
                    answer.style.maxHeight = answer.scrollHeight + "px"; /* Abre la respuesta dinámicamente */
                    icon.classList.add('rotate-180'); /* Gira el ícono 180 grados */
                }
            });
        });

        // Lógica para las gráficas del Dashboard con Chart.js
        document.addEventListener('DOMContentLoaded', () => {
            // Opciones de configuración base para todas las gráficas
            const chartOptions = {
                responsive: true,
                maintainAspectRatio: false, /* Permite que el tamaño del canvas se ajuste al contenedor */
                plugins: { 
                    legend: { 
                        position: 'bottom', /* Leyenda en la parte inferior */
                        labels: { 
                            color: '#4B5563', /* Color de texto gris oscuro */
                            font: { family: "'Inter', sans-serif" } 
                        } 
                    } 
                },
                scales: {
                    y: { 
                        beginAtZero: true, /* Eje Y empieza en cero */
                        grid: { color: '#E5E7EB' }, /* Color de las líneas de la cuadrícula */
                        ticks: { color: '#4B5563' } /* Color del texto de los ticks del eje Y */
                    },
                    x: { 
                        grid: { display: false }, /* Oculta las líneas de la cuadrícula en el eje X */
                        ticks: { color: '#4B5563' } /* Color del texto de los ticks del eje X */
                    }
                }
            };
            
            // Gráfica de Ahorro de Agua (Tipo Dona)
            const ahorroCtx = document.getElementById('ahorroAguaChart')?.getContext('2d');
            if(ahorroCtx) new Chart(ahorroCtx, {
                type: 'doughnut',
                data: {
                    labels: ['Agua Ahorrada', 'Agua Usada'],
                    datasets: [{ 
                        label: 'Ahorro de Agua', 
                        data: [55, 45], /* Datos de ejemplo: 55% ahorrado, 45% usado */
                        backgroundColor: ['#10B981', '#E5E7EB'], /* Colores para las secciones */
                        borderColor: ['#ffffff'], 
                        borderWidth: 4, 
                        hoverOffset: 8 
                    }]
                },
                options: { ...chartOptions, cutout: '70%' } /* Opciones específicas de la gráfica de dona */
            });

            // Gráfica de Productividad (Tipo Barras)
            const prodCtx = document.getElementById('productividadChart')?.getContext('2d');
            if(prodCtx) new Chart(prodCtx, {
                type: 'bar',
                data: {
                    labels: ['Rendimiento', 'Biomasa'],
                    datasets: [
                        { 
                            label: 'Sin Evida', 
                            data: [100, 100], 
                            backgroundColor: '#9CA3AF', /* Gris medio */
                            borderRadius: 6 
                        }, 
                        { 
                            label: 'Con Evida', 
                            data: [165, 125], /* Incremento del 65% y 25% */
                            backgroundColor: '#10B981', /* Verde esmeralda */
                            borderRadius: 6 
                        }
                    ]
                },
                options: chartOptions /* Usa las opciones base */
            });

            // Gráfica de Eficiencia en Uso de Fertilizantes (Tipo Línea)
            const nutriCtx = document.getElementById('nutrientesChart')?.getContext('2d');
            if(nutriCtx) new Chart(nutriCtx, {
                type: 'line',
                data: {
                    labels: ['Inicio', 'Mitad Ciclo', 'Cosecha'],
                    datasets: [
                        { 
                            label: 'Aprovechamiento Sin Evida', 
                            data: [30, 35, 38], 
                            borderColor: '#9CA3AF', 
                            tension: 0.4, 
                            fill: false /* Sin relleno bajo la línea */
                        },
                        { 
                            label: 'Aprovechamiento Con Evida', 
                            data: [50, 60, 62], 
                            borderColor: '#10B981', 
                            backgroundColor: 'rgba(16, 185, 129, 0.1)', 
                            tension: 0.4, 
                            fill: true /* Con relleno bajo la línea */
                        }
                    ]
                },
                options: chartOptions /* Usa las opciones base */
            });
        });
    </script>

</body>
</html>
