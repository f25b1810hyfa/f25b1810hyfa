## Hi there 👋

<!--
**f25b1810hyfa/f25b1810hyfa** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
--> <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MADA Paddy Canopy Growth & Derivatives Optimizer</title>
    <!-- Chart.js CDN -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Tailwind CSS for modern styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .math-font { font-family: 'Times New Roman', Times, serif; font-style: italic; }
    </style>
</head>
<body class="bg-gray-50 min-h-screen text-gray-800 font-sans">

    <!-- Header Section -->
    <header class="bg-emerald-700 text-white py-6 px-4 shadow-md">
        <div class="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center">
            <div>
                <h1 class="text-2xl font-bold tracking-tight">MADA Paddy Canopy Growth Tracker</h1>
                <p class="text-emerald-100 text-sm mt-1">Application of Calculus in Sustainable Food Security (SFM)</p>
            </div>
            <div class="mt-4 md:mt-0 bg-emerald-800 px-4 py-2 rounded-lg text-xs text-emerald-200 border border-emerald-600">
                <strong>Target Field:</strong> Crop Phenology & Smart Agriculture (Malaysia)
            </div>
        </div>
    </header>

    <!-- Main Content Grid -->
    <main class="max-w-6xl mx-auto px-4 py-8 grid grid-cols-1 lg:grid-cols-3 gap-8">
        
        <!-- Left Sidebar: Explanations & Formulas -->
        <div class="lg:col-span-1 space-y-6">
            
            <!-- Bioscience Context Box -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                <h2 class="text-lg font-semibold text-emerald-800 mb-3 flex items-center">
                    🌿 Scenario & Food Security Context
                </h2>
                <p class="text-sm text-gray-600 leading-relaxed mb-3">
                    In Malaysia, ensuring the <strong>Self-Sufficiency Level (SSL)</strong> for rice is paramount for national food security. The Muda Agricultural Development Authority (MADA) contributes approximately 38.8% of national production.
                </p>
                <p class="text-sm text-gray-600 leading-relaxed">
                    To optimize fertilizer schedules and forecast yields, <strong>MARDI</strong> uses precision farming frameworks that monitor the <strong>Green Area Index (GAI)</strong>. GAI measures leaf canopy volume per unit of ground. By understanding the <em>rate of change (derivative)</em> of GAI, agronomists target exact days when nitrogen uptake parameters are at peak velocity.
                </p>
                <div class="mt-3 pt-3 border-t border-gray-100 text-xs text-gray-500">
                    <strong>Data References:</strong> 
                    <ul class="list-disc pl-4 mt-1 space-y-1">
                        <li>MARDI Precision Paddy Package (Bakar, 2020)</li>
                        <li>MADA System Dynamics Assessment (Zainal Abidin et al., 2023)</li>
                    </ul>
                </div>
            </div>

            <!-- Calculus Mathematical Formulation Box -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                <h2 class="text-lg font-semibold text-blue-800 mb-3 flex items-center">
                    📐 Calculus Framework
                </h2>
                
                <!-- Function Formula -->
                <div class="mb-4 bg-gray-50 p-3 rounded-lg border border-gray-100">
                    <span class="text-xs text-gray-500 block font-semibold uppercase">Canopy Growth Curve, <span class="math-font">f(x)</span>:</span>
                    <div class="text-base font-mono text-center my-1 text-gray-800">
                        f(x) = L / (1 + e<sup>-k(x - x₀)</sup>)
                    </div>
                    <span class="text-xs text-gray-500 block mt-1">
                        Where maximum capacity <span class="math-font">L</span> = 5.5 GAI, growth rate coefficient <span class="math-font">k</span> = 0.09, and mid-inflection point <span class="math-font">x₀</span> = 55 days.
                    </span>
                </div>

                <!-- Derivative Formula -->
                <div class="bg-gray-50 p-3 rounded-lg border border-gray-100">
                    <span class="text-xs text-blue-600 block font-semibold uppercase">Instantaneous Rate of Change, <span class="math-font">f'(x)</span>:</span>
                    <div class="text-base font-mono text-center my-1 text-blue-700 font-bold">
                        f'(x) = [L · k · e<sup>-k(x - x₀)</sup>] / (1 + e<sup>-k(x - x₀)</sup>)<sup>2</sup>
                    </div>
                    <span class="text-xs text-gray-500 block mt-1">
                        Yields the exact vegetative velocity in <strong>GAI units/day</strong> at any specific Day of Year (DAT).
                    </span>
                </div>
            </div>

        </div>

        <!-- Right Side: Interactive Chart & Dynamic Output -->
        <div class="lg:col-span-2 space-y-6">
            
            <!-- Graph Box -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center mb-4">
                    <div>
                        <h2 class="text-xl font-bold text-gray-800">Paddy Canopy Expansion Profile</h2>
                        <p class="text-xs text-gray-500">Click anywhere inside the chart region to calculate the derivative at that specific point.</p>
                    </div>
                    <span class="mt-2 sm:mt-0 bg-blue-100 text-blue-800 font-semibold px-2.5 py-1 rounded-full text-xs">
                        Interactive Calculus Mode
                    </span>
                </div>

                <div class="relative w-full h-[400px]">
                    <canvas id="growthChart"></canvas>
                </div>
            </div>

            <!-- Dynamic Derivative Calculation Display Window -->
            <div id="inspectorPanel" class="bg-gradient-to-r from-slate-800 to-slate-900 text-white p-6 rounded-xl shadow-md border border-slate-700 transition-all duration-300 transform">
                <div id="placeholderText" class="text-center py-4 text-slate-400 text-sm">
                    💡 Click on the chart timeline coordinates above to trigger the Bioscience Derivative Calculator.
                </div>
                <div id="calcOutput" class="hidden">
                    <div class="flex flex-wrap items-center justify-between border-b border-slate-700 pb-3 mb-4">
                        <div>
                            <span class="text-xs font-semibold uppercase tracking-wider text-emerald-400">Selected Coordinate Baseline</span>
                            <h3 class="text-2xl font-black mt-0.5" id="outDay">Day 0 (DAT)</h3>
                        </div>
                        <div class="text-right">
                            <span class="text-xs font-semibold uppercase tracking-wider text-blue-400">Calculated Derivative f'(x)</span>
                            <div class="text-2xl font-black text-blue-400 mt-0.5" id="outDerivative">+0.000 GAI/day</div>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                        <div class="bg-slate-800/50 p-3 rounded-lg border border-slate-700">
                            <span class="text-xs text-slate-400 block">Canopy Status f(x)</span>
                            <span class="text-lg font-bold text-white" id="outGAI">0.00 GAI</span>
                        </div>
                        <div class="md:col-span-2 bg-slate-800/50 p-3 rounded-lg border border-slate-700">
                            <span class="text-xs text-amber-400 font-bold block mb-0.5">🌾 Food Security Translation (Layman's Terms)</span>
                            <p class="text-sm text-slate-200 leading-snug" id="outExplanation">No data generated yet.</p>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </main>

    <!-- Footer Elements -->
    <footer class="bg-gray-100 border-t border-gray-200 py-6 text-center text-xs text-gray-500 mt-12">
        MADA Phenology App Framework • Created for Sustainable Food Security Studies. Built with Chart.js Animation Engine.
    </footer>

    <!-- Interactive Logic Script -->
    <script>
        // Parameters for realistic MADA paddy lifecycle logistic modeling
        const L = 5.5;    // Maximum canopy density (Green Area Index ceiling)
        const k = 0.09;   // Logistic growth parameter scale
        const x0 = 55;    // Growth inflection maximum centerpoint (Days After Transplanting - DAT)

        // Math Equation Functions
        function getGAI(x) {
            return L / (1 + Math.exp(-k * (x - x0)));
        }

        function getDerivative(x) {
            const expTerm = Math.exp(-k * (x - x0));
            const denominator = Math.pow(1 + expTerm, 2);
            return (L * k * expTerm) / denominator;
        }

        // Generate Dataset Array for Lifecycle (0 to 110 Days)
        const daysData = [];
        const gaiPoints = [];
        const derivativePoints = [];

        for (let day = 0; day <= 110; day += 2) {
            daysData.push(day);
            gaiPoints.push(getGAI(day));
            derivativePoints.push(getDerivative(day));
        }

        // Initialize Canvas Element contexts
        const ctx = document.getElementById('growthChart').getContext('2d');
        
        // Define Chart Component Architecture
        const growthChart = new Chart(ctx, {
            type: 'line',
            data: {
                labels: daysData,
                datasets: [
                    {
                        label: 'Canopy Density f(x) [GAI]',
                        data: gaiPoints,
                        borderColor: '#059669',
                        backgroundColor: 'rgba(5, 150, 105, 0.06)',
                        borderWidth: 3,
                        yAxisID: 'yGAI',
                        fill: true,
                        tension: 0.2,
                        pointRadius: 0,
                        pointHoverRadius: 6
                    },
                    {
                        label: "Growth Acceleration Speed f'(x) [GAI/Day]",
                        data: derivativePoints,
                        borderColor: '#2563eb',
                        borderDash: [5, 5],
                        borderWidth: 2,
                        yAxisID: 'yRate',
                        fill: false,
                        tension: 0.2,
                        pointRadius: 0,
                        pointHoverRadius: 6
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                interaction: {
                    mode: 'index',
                    intersect: false,
                },
                plugins: {
                    legend: {
                        position: 'top',
                        labels: { boxWidth: 20, font: { size: 12 } }
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                let label = context.dataset.label || '';
                                if (label) label += ': ';
                                label += context.parsed.y.toFixed(3);
                                return label;
                            }
                        }
                    }
                },
                scales: {
                    x: {
                        title: {
                            display: true,
                            text: 'Days After Transplanting / Sowing (DAT)',
                            font: { weight: 'bold' }
                        },
                        grid: { color: '#f3f4f6' }
                    },
                    yGAI: {
                        type: 'linear',
                        display: true,
                        position: 'left',
                        title: {
                            display: true,
                            text: 'Green Area Index (m² leaf / m² ground)',
                            font: { color: '#059669', weight: 'bold' }
                        },
                        min: 0,
                        max: 6
                    },
                    yRate: {
                        type: 'linear',
                        display: true,
                        position: 'right',
                        title: {
                            display: true,
                            text: 'Rate of Growth Dynamics (f\'(x) per day)',
                            font: { color: '#2563eb', weight: 'bold' }
                        },
                        min: 0,
                        max: 0.2,
                        grid: { drawOnChartArea: false }
                    }
                },
                // Trigger action handling upon click interactions 
                onClick: (e) => {
                    const points = growthChart.getElementsAtEventForMode(e, 'index', { intersect: false }, true);
                    if (points.length > 0) {
                        const index = points[0].index;
                        const targetDay = daysData[index];
                        processCalculusDiagnostic(targetDay);
                    }
                }
            }
        });

        // Compute and translate specific calculation details to layman output strings
        function processCalculusDiagnostic(day) {
            const currentGAI = getGAI(day);
            const currentRate = getDerivative(day);

            // Access DOM Element containers
            document.getElementById('placeholderText').classList.add('hidden');
            const outputPanel = document.getElementById('calcOutput');
            outputPanel.classList.remove('hidden');

            // Inject numerical calculations
            document.getElementById('outDay').innerText = `Day ${day} (DAT)`;
            document.getElementById('outDerivative').innerText = `+${currentRate.toFixed(4)} GAI / Day`;
            document.getElementById('outGAI').innerText = `${currentGAI.toFixed(2)} GAI`;

            // Evaluate conditional translations based on crop parameters
            let briefTranslation = "";
            if (day < 35) {
                briefTranslation = `The canopy is establishing roots slowly. The rate of change is minimal (${currentRate.toFixed(3)}). Fertilizer added now runs off easily; wait for peak vegetative speed.`;
            } else if (day >= 35 && day <= 70) {
                if (day < 55) {
                    briefTranslation = `The growth velocity is accelerating! The plant is in exponential surge mode. It demands critical nitrogen inputs immediately to ensure future grain density.`;
                } else if (day === 54 || day === 56 || day === 55) {
                    briefTranslation = `Inflection Point Reached! The absolute peak rate of canopy expansion (${currentRate.toFixed(3)} GAI/day). The crop is running at max efficiency.`;
                } else {
                    briefTranslation = `Growth velocity is starting to decelerate from its historical peak, but expansion continues as the plants pivot nutrients into hidden reproductive panicle structures.`;
                }
            } else {
                briefTranslation = `The derivative drops to zero (${currentRate.toFixed(3)}). Leaf growth is completed. The plant enters grain filling stage, moving sugars directly into rice kernels for harvest preparation.`;
            }

            document.getElementById('outExplanation').innerText = briefTranslation;
        }
    </script>
</body>
</html>

