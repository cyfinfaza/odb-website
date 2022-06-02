<head>
	<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
	<script type="text/javascript">
		google.charts.load('current', { packages: ['corechart'] });
		google.charts.setOnLoadCallback(drawChart);

		function drawChart() {
			var data = google.visualization.arrayToDataTable([
				['Month', 'Meals'],
				['January', 8864],
				['Febuary', 8847],
				['March', 8890],
				['April', 8859],
				['May', 8893],
				['June', 8867],
				['July', 8890],
				['August', 8874],
				['September', 8902],
				['October', 8864],
				['November', 8884],
				['December', 8874]
			]);

			var options = {
				title: 'Meals Donated',
				curveType: 'function',
				legend: { position: 'bottom' }
			};

			var chart = new google.visualization.LineChart(document.getElementById('curve_chart'));

			chart.draw(data, options);
		}
	</script>
</head>
<body>
	<div id="curve_chart" style="width: 900px; height: 500px" />
</body>
