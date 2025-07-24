<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Landscape of Enterprise Data Architectures</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #1e293b;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 400px;
        }
        @media (max-width: 768px) {
            .chart-container {
                height: 300px;
                max-height: 350px;
            }
        }
        .gradient-text {
            background: linear-gradient(to right, #F72585, #3A0CA3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .flow-diagram-arrow {
            font-size: 2rem;
            color: #94a3b8;
            line-height: 1;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            padding: 1.5rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .icon-style {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
    </style>
</head>
<body class="antialiased">

    <div class="container mx-auto p-4 md:p-8">

        <header class="text-center my-12">
            <h1 class="text-4xl md:text-6xl font-black tracking-tight gradient-text">The Evolving Landscape of</h1>
            <h2 class="text-4xl md:text-6xl font-black tracking-tight text-slate-800">Enterprise Data Architectures</h2>
            <p class="mt-6 max-w-3xl mx-auto text-lg text-slate-600">From monolithic warehouses to decentralized meshes, the way organizations manage data is undergoing a profound transformation. This infographic explores the key architectures shaping the modern data ecosystem, their applications, and the challenges they address.</p>
        </header>

        <main>
            <section id="architectures" class="my-16">
                <h3 class="text-3xl font-bold text-center mb-12 text-slate-700">A Spectrum of Modern Data Architectures</h3>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">

                    <div class="card col-span-1 lg:col-span-2">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                            <div>
                                <h4 class="text-2xl font-bold mb-2" style="color: #3A0CA3;">1. Traditional Data Warehouse</h4>
                                <p class="text-slate-600 mb-4">The foundational architecture for historical analysis, designed for structured data and business intelligence. It consolidates data from various sources into a central repository for consistent reporting.</p>
                                <div class="mt-6">
                                    <h5 class="font-semibold mb-2 text-slate-700">Core Process: ETL (Extract, Transform, Load)</h5>
                                    <div class="flex flex-wrap items-center justify-center md:justify-start gap-2 text-center">
                                        <div class="p-2 bg-slate-100 rounded-lg text-sm font-medium">Sources</div>
                                        <div class="flow-diagram-arrow">&rarr;</div>
                                        <div class="p-2 bg-slate-100 rounded-lg text-sm font-medium">Staging</div>
                                        <div class="flow-diagram-arrow">&rarr;</div>
                                        <div class="p-2 bg-blue-100 rounded-lg text-sm font-bold text-blue-800">Warehouse</div>
                                        <div class="flow-diagram-arrow">&rarr;</div>
                                        <div class="p-2 bg-slate-100 rounded-lg text-sm font-medium">Data Marts</div>
                                        <div class="flow-diagram-arrow">&rarr;</div>
                                        <div class="p-2 bg-slate-100 rounded-lg text-sm font-medium">BI Tools</div>
                                    </div>
                                    <p class="mt-4 text-sm text-slate-500"><strong class="text-slate-600">Limitations:</strong> Struggles with unstructured data, high costs, and scalability constraints due to tightly coupled compute and storage.</p>
                                </div>
                            </div>
                            <div class="chart-container h-80 md:h-96">
                                <canvas id="warehouseChart"></canvas>
                            </div>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h4 class="text-2xl font-bold mb-2" style="color: #00A6ED;">2. Data Lake</h4>
                        <p class="text-slate-600 mb-4">A vast, centralized repository that stores raw data in its native format. Its flexible "schema-on-read" approach makes it ideal for big data analytics and machine learning experimentation.</p>
                        <div class="chart-container h-80 md:h-96">
                            <canvas id="lakeChart"></canvas>
                        </div>
                        <p class="mt-4 text-sm text-slate-500 text-center"><strong class="text-red-500">⚠️ Key Challenge:</strong> Without strong governance, data lakes can become unusable "data swamps."</p>
                    </div>

                    <div class="card">
                        <h4 class="text-2xl font-bold mb-2" style="color: #7FB800;">3. Data Lakehouse</h4>
                        <p class="text-slate-600 mb-4">A hybrid architecture combining the low-cost, flexible storage of a data lake with the management features and reliability of a data warehouse. It provides a unified platform for both BI and AI.</p>
                        <div class="chart-container h-80 md:h-96">
                             <canvas id="lakehouseChart"></canvas>
                        </div>
                        <p class="mt-4 text-sm text-slate-500 text-center"><strong class="text-slate-600">Benefit:</strong> Enables ACID transactions and data versioning directly on the data lake, enhancing AI/ML readiness.</p>
                    </div>

                    <div class="card col-span-1 lg:col-span-2">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                             <div>
                                <h4 class="text-2xl font-bold mb-2" style="color: #F72585;">4. Data Mesh</h4>
                                <p class="text-slate-600 mb-4">A decentralized, domain-oriented approach that treats "data as a product." It shifts data ownership from a central team to domain-specific teams, fostering agility, scalability, and accountability.</p>
                                <div class="mt-6">
                                    <h5 class="font-semibold mb-2 text-slate-700">Organizational Shift</h5>
                                    <div class="flex justify-around items-start text-center">
                                        <div>
                                            <p class="font-bold">Centralized</p>
                                            <div class="mt-2 p-4 border-2 border-dashed border-slate-300 rounded-lg">
                                                <div class="p-2 bg-slate-200 rounded mb-2">Data Team</div>
                                                <div class="flow-diagram-arrow transform rotate-90"></div>
                                                <div class="flex gap-2">
                                                    <div class="p-2 bg-slate-100 rounded text-xs">Domain A</div>
                                                    <div class="p-2 bg-slate-100 rounded text-xs">Domain B</div>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="text-3xl font-bold mx-4 mt-16" style="color: #F72585;">&rarr;</div>
                                        <div>
                                            <p class="font-bold">Decentralized (Mesh)</p>
                                            <div class="mt-2 p-4 border-2 border-dashed border-pink-300 rounded-lg">
                                                <div class="p-2 bg-pink-100 rounded mb-2 text-xs">Domain A Data Product</div>
                                                <div class="p-2 bg-pink-100 rounded text-xs">Domain B Data Product</div>
                                            </div>
                                        </div>
                                    </div>
                                    <p class="mt-4 text-sm text-slate-500"><strong class="text-slate-600">Challenge:</strong> Requires a significant cultural shift and robust federated governance to maintain consistency.</p>
                                </div>
                            </div>
                            <div class="chart-container h-80 md:h-96">
                                <canvas id="meshChart"></canvas>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <h4 class="text-2xl font-bold mb-2" style="color: #FFB400;">5. Data Fabric</h4>
                        <p class="text-slate-600 mb-4">An intelligent, metadata-driven architecture that connects and unifies data from disparate sources without moving it. It creates a virtual data layer for seamless access and governance.</p>
                        <div class="text-center my-8">
                            <div class="icon-style" style="color: #FFB400;">🌐</div>
                            <p class="text-5xl font-black text-slate-800">$12.91B</p>
                            <p class="text-slate-600 font-semibold">Projected Market by 2032</p>
                            <p class="mt-4 text-sm text-slate-500">Powered by active metadata and knowledge graphs to automate integration and enable self-service analytics.</p>
                        </div>
                    </div>

                    <div class="card">
                        <h4 class="text-2xl font-bold mb-2" style="color: #00A6ED;">6. Event-Driven & Streaming</h4>
                        <p class="text-slate-600 mb-4">Enables systems to react to events in real-time. This architecture is crucial for applications requiring immediate insights, such as fraud detection, IoT monitoring, and live personalization.</p>
                         <div class="chart-container h-80 md:h-96">
                            <canvas id="streamingChart"></canvas>
                        </div>
                        <p class="mt-4 text-sm text-slate-500 text-center"><strong class="text-slate-600">Principle:</strong> Loose coupling of components (producers, brokers, consumers) allows for superior scalability and resilience.</p>
                    </div>
                </div>
            </section>

            <section id="gaps" class="my-24">
                <h3 class="text-3xl font-bold text-center mb-4 text-slate-700">Industry-Wide Gaps & Unmet Needs</h3>
                <p class="text-center max-w-3xl mx-auto text-slate-600 mb-12">Despite architectural advancements, several fundamental challenges persist across the data landscape, highlighting the ongoing quest for truly seamless, governed, and value-driven data ecosystems.</p>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="card text-center">
                        <div class="icon-style" style="color: #F72585;">🛡️</div>
                        <h5 class="font-bold text-lg mb-2">Quality & Governance</h5>
                        <p class="text-slate-600 text-sm">Ensuring consistent data quality and robust governance across increasingly distributed and heterogeneous systems remains a formidable hurdle.</p>
                    </div>
                    <div class="card text-center">
                        <div class="icon-style" style="color: #7FB800;">🔗</div>
                        <h5 class="font-bold text-lg mb-2">Interoperability</h5>
                        <p class="text-slate-600 text-sm">Achieving seamless integration between modern platforms and legacy infrastructure continues to be complex, costly, and time-consuming.</p>
                    </div>
                    <div class="card text-center">
                        <div class="icon-style" style="color: #3A0CA3;">🤖</div>
                        <h5 class="font-bold text-lg mb-2">AI/ML Operationalization</h5>
                        <p class="text-slate-600 text-sm">Bridging the gap from experimental models to reliable, production-ready AI at scale is hindered by data silos, scalability issues, and governance gaps.</p>
                    </div>
                    <div class="card text-center">
                        <div class="icon-style" style="color: #FFB400;">💰</div>
                        <h5 class="font-bold text-lg mb-2">Cost vs. Value</h5>
                        <p class="text-slate-600 text-sm">Organizations struggle to balance the high implementation and maintenance costs of advanced architectures with demonstrable ROI.</p>
                    </div>
                    <div class="card text-center">
                        <div class="icon-style" style="color: #00A6ED;">👥</div>
                        <h5 class="font-bold text-lg mb-2">Talent & Culture</h5>
                        <p class="text-slate-600 text-sm">A pervasive need for skilled talent and a profound cultural shift towards data-as-a-product thinking are critical for success.</p>
                    </div>
                    <div class="card text-center bg-slate-800 text-white">
                         <div class="icon-style">💡</div>
                        <h5 class="font-bold text-lg mb-2">The Path Forward</h5>
                        <p class="text-slate-300 text-sm">The future lies in hybrid approaches, AI-driven automation, and semantic layers that unify data while balancing centralized control with decentralized agility.</p>
                    </div>
                </div>
            </section>
        </main>

        <footer class="text-center py-8 mt-12 border-t border-slate-200">
            <p class="text-slate-500">Infographic by Canvas Infographics. Data synthesized from industry analysis.</p>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const FONT_COLOR = '#374151';
            const GRID_COLOR = '#e5e7eb';
            const PALETTE = {
                blue: '#00A6ED',
                green: '#7FB800',
                yellow: '#FFB400',
                pink: '#F72585',
                purple: '#3A0CA3',
                slate: '#64748b'
            };

            const wrapLabel = (label, maxWidth = 16) => {
                if (label.length <= maxWidth) {
                    return label;
                }
                const words = label.split(' ');
                const lines = [];
                let currentLine = '';
                for (const word of words) {
                    if ((currentLine + ' ' + word).trim().length > maxWidth) {
                        lines.push(currentLine.trim());
                        currentLine = word;
                    } else {
                        currentLine = (currentLine + ' ' + word).trim();
                    }
                }
                if (currentLine) {
                    lines.push(currentLine.trim());
                }
                return lines;
            };

            const tooltipTitleCallback = (tooltipItems) => {
                const item = tooltipItems[0];
                let label = item.chart.data.labels[item.dataIndex];
                if (Array.isArray(label)) {
                    return label.join(' ');
                }
                return label;
            };
            
            const defaultChartOptions = {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        labels: {
                            color: FONT_COLOR,
                            font: {
                                family: "'Inter', sans-serif"
                            }
                        }
                    },
                    tooltip: {
                        callbacks: {
                            title: tooltipTitleCallback
                        },
                        titleFont: {
                           family: "'Inter', sans-serif"
                        },
                        bodyFont: {
                           family: "'Inter', sans-serif"
                        }
                    }
                },
                scales: {
                    x: {
                        ticks: { color: FONT_COLOR, font: { family: "'Inter', sans-serif" } },
                        grid: { color: GRID_COLOR }
                    },
                    y: {
                        ticks: { color: FONT_COLOR, font: { family: "'Inter', sans-serif" } },
                        grid: { color: GRID_COLOR }
                    }
                }
            };

            const warehouseCtx = document.getElementById('warehouseChart');
            if(warehouseCtx) {
                new Chart(warehouseCtx, {
                    type: 'doughnut',
                    data: {
                        labels: ['BI & Reporting', 'Legacy Integration', 'Financial Risk', 'Operations'],
                        datasets: [{
                            label: 'Primary Use Cases',
                            data: [65, 15, 10, 10],
                            backgroundColor: [PALETTE.purple, PALETTE.slate, PALETTE.blue, PALETTE.green],
                            borderColor: '#ffffff',
                            borderWidth: 4
                        }]
                    },
                    options: {
                        ...defaultChartOptions,
                        plugins: { ...defaultChartOptions.plugins, legend: { position: 'top' } },
                        scales: { x: { display: false }, y: { display: false } }
                    }
                });
            }

            const lakeCtx = document.getElementById('lakeChart');
            if (lakeCtx) {
                new Chart(lakeCtx, {
                    type: 'bar',
                    data: {
                        labels: ['Scalability', 'Flexibility', 'AI/ML Support', 'Low Cost'],
                        datasets: [{
                            label: 'Key Strengths',
                            data: [95, 90, 85, 80],
                            backgroundColor: PALETTE.blue,
                            borderRadius: 4
                        }]
                    },
                    options: {
                        ...defaultChartOptions,
                        indexAxis: 'y',
                        plugins: { ...defaultChartOptions.plugins, legend: { display: false } },
                    }
                });
            }

            const lakehouseCtx = document.getElementById('lakehouseChart');
            if (lakehouseCtx) {
                new Chart(lakehouseCtx, {
                    type: 'radar',
                    data: {
                        labels: ['AI/ML Readiness', 'Governance', 'Flexibility', 'Cost Efficiency', 'Performance'],
                        datasets: [
                            {
                                label: 'Lakehouse',
                                data: [9, 7, 8, 8, 8],
                                fill: true,
                                backgroundColor: 'rgba(127, 184, 0, 0.2)',
                                borderColor: PALETTE.green,
                                pointBackgroundColor: PALETTE.green
                            },
                            {
                                label: 'Data Lake',
                                data: [8, 3, 9, 9, 6],
                                fill: true,
                                backgroundColor: 'rgba(0, 166, 237, 0.2)',
                                borderColor: PALETTE.blue,
                                pointBackgroundColor: PALETTE.blue
                            },
                             {
                                label: 'Data Warehouse',
                                data: [3, 8, 4, 5, 9],
                                fill: true,
                                backgroundColor: 'rgba(58, 12, 163, 0.2)',
                                borderColor: PALETTE.purple,
                                pointBackgroundColor: PALETTE.purple
                            }
                        ]
                    },
                    options: {
                        ...defaultChartOptions,
                        scales: {
                            r: {
                                angleLines: { color: GRID_COLOR },
                                grid: { color: GRID_COLOR },
                                pointLabels: { font: { size: 12, family: "'Inter', sans-serif" }, color: FONT_COLOR },
                                ticks: { backdropColor: '#f8fafc', color: FONT_COLOR }
                            }
                        }
                    }
                });
            }

            const meshCtx = document.getElementById('meshChart');
            if (meshCtx) {
                new Chart(meshCtx, {
                    type: 'bar',
                    data: {
                        labels: ['Increase Scalability & Agility', 'Improve Data Quality & Trust', 'Accelerate Time to Value', 'Empower Domain Teams'],
                        datasets: [{
                            label: 'Key Adoption Drivers',
                            data: [90, 80, 85, 95],
                            backgroundColor: PALETTE.pink,
                            borderRadius: 4
                        }]
                    },
                    options: {
                        ...defaultChartOptions,
                        plugins: { ...defaultChartOptions.plugins, legend: { display: false } },
                        scales: {
                            x: {
                                ticks: {
                                    callback: function(value) {
                                        const label = this.getLabelForValue(value);
                                        return wrapLabel(label, 20);
                                    }
                                }
                            }
                        }
                    }
                });
            }
            
            const streamingCtx = document.getElementById('streamingChart');
            if (streamingCtx) {
                new Chart(streamingCtx, {
                    type: 'bar',
                    data: {
                        labels: ['Finance (Fraud Detection)', 'Retail (Personalization)', 'Healthcare (Monitoring)', 'Manufacturing (IoT)'],
                        datasets: [{
                            label: 'Adoption by Use Case',
                            data: [95, 90, 80, 85],
                            backgroundColor: [PALETTE.blue, PALETTE.pink, PALETTE.green, PALETTE.slate],
                            borderRadius: 4
                        }]
                    },
                    options: {
                        ...defaultChartOptions,
                        plugins: { ...defaultChartOptions.plugins, legend: { display: false } },
                         scales: {
                            x: {
                                ticks: {
                                    callback: function(value) {
                                        const label = this.getLabelForValue(value);
                                        return wrapLabel(label, 18);
                                    }
                                }
                            }
                        }
                    }
                });
            }
        });
    </script>
</body>
</html>
