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
                <a href="#problema" class="text-gray-600 hover:text-emerald-600 transition duration-300">El Problema</a>
                <a href="#solucion" class="text-gray-600 hover:text-emerald-600 transition duration-300">La Solución</a>
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
            <a href="#problema" class="block py-2 px-4 text-sm hover:bg-gray-100">El Problema</a>
            <a href="#solucion" class="block py-2 px-4 text-sm hover:bg-gray-100">La Solución</a>
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
        
        <!-- Sección El Problema que Resolvemos -->
        <section id="problema" class="py-20 fade-in-section">
            <div class="container mx-auto px-6 text-center">
                <h2 class="text-4xl font-bold text-gray-900">El Problema que Resolvemos</h2>
                <p class="mt-4 text-lg text-gray-600 max-w-3xl mx-auto">México enfrenta una crisis hídrica severa que afecta directamente la productividad agrícola y la seguridad alimentaria de millones.</p>
                <div class="mt-12 grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="bg-white p-8 rounded-2xl shadow-lg">
                        <p class="text-6xl font-extrabold gradient-text">68%</p>
                        <p class="mt-2 text-gray-700 font-semibold">Del territorio mexicano presenta sequía</p>
                    </div>
                    <div class="bg-white p-8 rounded-2xl shadow-lg">
                        <p class="text-6xl font-extrabold gradient-text">76%</p>
                        <p class="mt-2 text-gray-700 font-semibold">Del agua se destina a actividades agrícolas</p>
                    </div>
                    <div class="bg-white p-8 rounded-2xl shadow-lg">
                        <p class="text-6xl font-extrabold gradient-text">40%</p>
                        <p class="mt-2 text-gray-700 font-semibold">De pérdida en sistemas de riego tradicionales</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección Nuestra Solución -->
        <section id="solucion" class="py-20 bg-white fade-in-section">
            <div class="container mx-auto px-6">
                 <div class="text-center mb-12">
                    <h2 class="text-4xl font-bold text-gray-900">Nuestra Solución: Poliacrilato de Potasio</h2>
                    <p class="mt-4 text-lg text-gray-600">Tecnología superabsorbente, eficiente y sostenible.</p>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Tarjeta de Beneficio 1: Súper Absorción -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                           <p class="text-3xl font-bold text-emerald-600">500x</p>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Súper Absorción</h3>
                        <p class="text-gray-600">Absorbe hasta 500 veces su peso en agua.</p>
                    </div>
                     <!-- Tarjeta de Beneficio 2: Liberación Lenta -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                             <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Liberación Lenta</h3>
                        <p class="text-gray-600">Liberación gradual de agua y nutrientes según la necesidad de la planta.</p>
                    </div>
                     <!-- Tarjeta de Beneficio 3: Durabilidad -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                             <p class="text-2xl font-bold text-emerald-600">5-8</p>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Durabilidad</h3>
                        <p class="text-gray-600">Efectivo en el suelo por un periodo de 5 a 8 años.</p>
                    </div>
                     <!-- Tarjeta de Beneficio 4: Biodegradable -->
                    <div class="bg-white p-8 rounded-2xl shadow-lg text-center transform hover:-translate-y-2 transition duration-300">
                        <div class="bg-emerald-100 rounded-full w-16 h-16 flex items-center justify-center mx-auto mb-4">
                           <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">100% Seguro</h3>
                        <p class="text-gray-600">Biodegradable, se descompone de forma natural sin dejar residuos.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección de Dashboard de Impacto -->
        <section id="dashboard" class="py-20 fade-in-section">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900">Dashboard de Impacto y Resultados</h2>
                    <p class="mt-4 text-lg text-gray-600">Datos que demuestran la eficacia de Evida Hydrogel.</p>
                </div>

                <!-- KPIs (Indicadores Clave de Desempeño) -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 mb-16 text-center">
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
                    <div class="bg-white p-6 rounded-2xl shadow-lg kpi-card-animation" style="animation-delay: 0.6s;">
                        <p class="text-5xl font-extrabold gradient-text">500x</p>
                        <p class="mt-2 text-gray-700 font-semibold">Capacidad de Retención</p>
                    </div>
                </div>

                <!-- Gráficas y Mapa de Impacto -->
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <div class="bg-white p-6 rounded-2xl shadow-lg">
                        <h3 class="font-bold text-lg mb-4 text-center">Ahorro de Agua por Cultivo</h3>
                        <div class="chart-container">
                            <canvas id="ahorroPorCultivoChart"></canvas>
                        </div>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-lg">
                        <h3 class="font-bold text-lg mb-4 text-center">Eficiencia en Uso de Fertilizantes</h3>
                        <div class="chart-container">
                            <canvas id="eficienciaNutrientesChart"></canvas>
                        </div>
                    </div>
                    <div class="lg:col-span-2 bg-white p-6 rounded-2xl shadow-lg">
                        <h3 class="font-bold text-lg mb-4 text-center">Incremento del Rendimiento a lo Largo del Tiempo</h3>
                        <div class="chart-container">
                            <canvas id="rendimientoTiempoChart"></canvas>
                        </div>
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

        <!-- Sección de Preguntas Frecuentes (FAQ) -->
        <section id="faq" class="py-20 fade-in-section">
            <div class="container mx-auto px-6 max-w-4xl">
                 <div class="text-center mb-12">
                    <h2 class="text-4xl font-bold text-gray-900">Preguntas Frecuentes</h2>
                    <p class="mt-4 text-lg text-gray-600">Resolvemos tus dudas más comunes.</p>
                </div>
                <div class="space-y-4">
                    <!-- Pregunta FAQ 1 -->
                    <div class="bg-white rounded-lg shadow">
                        <button class="faq-question w-full flex justify-between items-center text-left p-6 font-semibold text-lg focus:outline-none">
                            <span>¿El hidrogel es tóxico o daña el medio ambiente?</span>
                            <svg class="w-6 h-6 transform transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                        <div class="faq-answer px-6 pb-6 text-gray-600">
                            <p>No, nuestro producto es 100% seguro y no tóxico. Está diseñado para ser biodegradable, descomponiéndose de forma natural en el suelo sin dejar residuos perjudiciales, lo que lo hace una opción completamente sostenible.</p>
                        </div>
                    </div>
                     <!-- Pregunta FAQ 2 -->
                    <div class="bg-white rounded-lg shadow">
                        <button class="faq-question w-full flex justify-between items-center text-left p-6 font-semibold text-lg focus:outline-none">
                            <span>¿Cuánto tiempo dura el producto en el suelo?</span>
                            <svg class="w-6 h-6 transform transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                        <div class="faq-answer px-6 pb-6 text-gray-600">
                            <p>La efectividad de Evida Hydrogel puede durar entre 5 y 8 años en el suelo, dependiendo de las condiciones climáticas y el tipo de terreno. Durante este tiempo, seguirá absorbiendo y liberando agua en múltiples ciclos.</p>
                        </div>
                    </div>
                     <!-- Pregunta FAQ 3 -->
                    <div class="bg-white rounded-lg shadow">
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
                        <li><a href="#solucion" class="text-gray-400 hover:text-white">La Solución</a></li>
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
            
            // Gráfica de Ahorro de Agua por Cultivo (Barras)
            const ahorroCultivoCtx = document.getElementById('ahorroPorCultivoChart')?.getContext('2d');
            if(ahorroCultivoCtx) new Chart(ahorroCultivoCtx, {
                type: 'bar',
                data: {
                    labels: ['Maíz', 'Tomate', 'Frijol', 'Chile'],
                    datasets: [{
                        label: 'Riego Tradicional (%)',
                        data: [100, 100, 100, 100],
                        backgroundColor: '#9CA3AF',
                        borderRadius: 6
                    }, {
                        label: 'Con Evida Hydrogel (%)',
                        data: [55, 60, 50, 65], // Datos de ejemplo de ahorro
                        backgroundColor: '#10B981',
                        borderRadius: 6
                    }]
                },
                options: chartOptions
            });

            // Gráfica de Eficiencia en Uso de Fertilizantes (Barras)
            const eficienciaNutrientesCtx = document.getElementById('eficienciaNutrientesChart')?.getContext('2d');
            if(eficienciaNutrientesCtx) new Chart(eficienciaNutrientesCtx, {
                type: 'bar',
                data: {
                    labels: ['Nitrógeno', 'Fósforo', 'Potasio'],
                    datasets: [{
                        label: 'Aprovechamiento Tradicional (%)',
                        data: [45, 35, 40],
                        backgroundColor: '#9CA3AF',
                        borderRadius: 6
                    }, {
                        label: 'Aprovechamiento con Hydrogel (%)',
                        data: [77, 85, 100], // El 102% se representa como 100 para la escala
                        backgroundColor: '#10B981',
                        borderRadius: 6
                    }]
                },
                options: { ...chartOptions, indexAxis: 'y' } // Barras horizontales
            });

            // Gráfica de Incremento del Rendimiento (Línea)
            const rendimientoTiempoCtx = document.getElementById('rendimientoTiempoChart')?.getContext('2d');
            if(rendimientoTiempoCtx) new Chart(rendimientoTiempoCtx, {
                type: 'line',
                data: {
                    labels: ['Mes 1', 'Mes 2', 'Mes 3', 'Mes 4', 'Mes 5'],
                    datasets: [{ 
                        label: 'Rendimiento (%)', 
                        data: [10, 25, 40, 55, 65],
                        borderColor: '#10B981', 
                        backgroundColor: 'rgba(16, 185, 129, 0.1)', 
                        tension: 0.4, 
                        fill: true
                    }]
                },
                options: chartOptions
            });
        });
    </script>

</body>
</html>
