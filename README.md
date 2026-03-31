# Reporte_Junta_Final_Completo
Reporte
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Dashboard Financiero Integral - Montacargas SAS</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body { background-color: #f8f9fa; font-family: 'Segoe UI', sans-serif; }
        .header-bg { background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%); color: white; padding: 50px 0; border-radius: 0 0 30px 30px; margin-bottom: 30px; }
        .card { border: none; border-radius: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); margin-bottom: 25px; }
        .table-indicators thead { background-color: #1e3c72; color: white; font-size: 0.9rem; }
        .table-indicators td { font-size: 0.85rem; vertical-align: middle; }
        .indicator-explanation { background: #fff; border-left: 5px solid #2a5298; padding: 15px; border-radius: 5px; margin-bottom: 10px; }
        .highlight-row { background-color: #eef2f7; font-weight: bold; }
    </style>
</head>
<body>

<div class="header-bg text-center">
    <h1>ESTADOS FINANCIEROS E INDICADORES DE GESTIÓN</h1>
    <p class="lead">Análisis Profesional para Junta Directiva - SERVICIO TÉCNICO MONTACARGAS SAS</p>
</div>

<div class="container">
    
    <div class="row">
        <div class="col-12">
            <div class="card p-4">
                <h4 class="fw-bold mb-4 text-primary">📊 Indicadores Financieros (Datos Oficiales Excel)</h4>
                <div class="table-responsive">
                    <table class="table table-hover table-indicators text-center border">
                        <thead>
                            <tr>
                                <th class="text-start">Indicador / Ratio</th>
                                <th>2022</th>
                                <th>2023</th>
                                <th>2024</th>
                                <th>2025</th>
                                <th class="bg-success">Presup. 2026</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr class="highlight-row"><td>Rentabilidad del Patrimonio (ROE)</td><td>14.6%</td><td>10.0%</td><td>8.0%</td><td>9.1%</td><td>18.7%</td></tr>
                            <tr><td>Rendimiento Activo Total (ROA)</td><td>8.4%</td><td>5.7%</td><td>4.6%</td><td>5.4%</td><td>10.7%</td></tr>
                            <tr><td>Razón Corriente (Liquidez)</td><td>1.91</td><td>1.34</td><td>1.84</td><td>1.47</td><td>1.84</td></tr>
                            <tr><td>Prueba Ácida</td><td>1.33</td><td>0.70</td><td>0.68</td><td>0.90</td><td>0.68</td></tr>
                            <tr><td>Rotación de Activos</td><td>0.76</td><td>0.80</td><td>0.74</td><td>0.69</td><td>0.73</td></tr>
                            <tr class="highlight-row"><td>Nivel de Endeudamiento</td><td>2.34</td><td>2.35</td><td>2.34</td><td>2.45</td><td>2.35</td></tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <div class="row">
        <div class="col-md-6">
            <div class="card p-4">
                <h5>Tendencia de Rentabilidad (ROE vs ROA)</h5>
                <canvas id="chartRentabilidad"></canvas>
            </div>
        </div>
        <div class="col-md-6">
            <div class="card p-4">
                <h5>Eficiencia y Liquidez</h5>
                <canvas id="chartEficiencia"></canvas>
            </div>
        </div>
    </div>

    <div class="row mt-3">
        <div class="col-12">
            <div class="card p-4">
                <h4 class="fw-bold mb-3">💡 Explicación de Indicadores para los Socios</h4>
                
                <div class="indicator-explanation">
                    <strong>1. Liquidez (Razón Corriente 1.47):</strong> Por cada peso que la empresa debe pagar a corto plazo, tenemos $1.47 para respaldarlo. Aunque bajó frente a 2024 ($1.84), seguimos en un rango seguro (superior a 1.0).
                </div>
                
                <div class="indicator-explanation">
                    <strong>2. Rentabilidad (ROE 9.1%):</strong> El retorno sobre el capital de los socios mejoró respecto al año pasado. La proyección de 18.7% para 2026 es el gran reto de eficiencia que justifica el plan de expansión.
                </div>

                <div class="indicator-explanation">
                    <strong>3. Rotación de Activos (0.69):</strong> Es el indicador a vigilar. Significa que nuestra infraestructura está produciendo ventas por debajo de su potencial. El objetivo es subir a 0.73 en 2026 optimizando el uso de la flota.
                </div>

                <div class="indicator-explanation">
                    <strong>4. Endeudamiento (2.45):</strong> Refleja una estructura financiada en mayor medida por terceros. Es estable, pero nos obliga a mantener un flujo de caja constante para cumplir obligaciones.
                </div>
            </div>
        </div>
    </div>

    <div class="row">
        <div class="col-lg-8">
            <div class="card p-4">
                <h4 class="fw-bold mb-4">📈 Evolución de Ventas, Gastos y Gasto Financiero</h4>
                <canvas id="mainChart" height="150"></canvas>
            </div>
        </div>
        <div class="col-lg-4">
            <div class="card p-4 bg-dark text-white text-center">
                <h5 class="text-warning">Meta de Ventas 2026</h5>
                <h2 class="display-5 fw-bold">$3,714M</h2>
                <p class="small">Necesario para cubrir IPC + Aumento Salarial del 11%</p>
                <hr>
                <h6>Gasto Financiero 2025</h6>
                <h3 class="text-danger">$364.6M</h3>
                <p class="small">Reducción del 10% vs 2024</p>
            </div>
        </div>
    </div>
</div>

<script>
    // Gráfico Rentabilidad
    new Chart(document.getElementById('chartRentabilidad'), {
        type: 'line',
        data: {
            labels: ['2022', '2023', '2024', '2025', '2026 (P)'],
            datasets: [
                { label: 'ROE %', data: [14.6, 10.0, 8.0, 9.1, 18.7], borderColor: '#1e3c72', fill: false },
                { label: 'ROA %', data: [8.4, 5.7, 4.6, 5.4, 10.7], borderColor: '#e74c3c', fill: false }
            ]
        }
    });

    // Gráfico Eficiencia
    new Chart(document.getElementById('chartEficiencia'), {
        type: 'bar',
        data: {
            labels: ['2022', '2023', '2024', '2025'],
            datasets: [
                { label: 'Razón Corriente', data: [1.91, 1.34, 1.84, 1.47], backgroundColor: '#3498db' },
                { label: 'Rotación Activos', data: [0.76, 0.80, 0.74, 0.69], backgroundColor: '#2ecc71' }
            ]
        }
    });

    // Gráfico Ventas y Gastos
    new Chart(document.getElementById('mainChart'), {
        type: 'bar',
        data: {
            labels: ['2023', '2024', '2025', '2026 (P)'],
            datasets: [
                { label: 'Ventas', data: [3088, 3355, 3391, 3690], backgroundColor: '#1e3c72' },
                { label: 'Gastos Totales', data: [1278, 1466, 1350, 1612], backgroundColor: '#f39c12' },
                { label: 'Gasto Fin.', data: [368, 405, 364, 445], backgroundColor: '#e74c3c' }
            ]
        }
    });
</script>

</body>
</html>
