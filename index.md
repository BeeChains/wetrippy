
<html>
<head>
<title>hns.wetrippy/ | Cyber Matrix Roots</title>
<style>
 body {
 background-color: black;
 overflow: auto;
       }
		
 canvas {
 display: block;
 position: fixed;
 top: 0;
 left: 0;
 z-index: -1;
       }
</style>
</head>
<body>
<canvas id="matrix"></canvas>
	
<script>
    const canvas = document.getElementById('matrix');
    const context = canvas.getContext('2d');

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const columnWidth = 20; // Increase column width for more space between columns
    const columns = Math.floor(canvas.width / columnWidth);

    const goldenRatio = 1.61803398875;
    const rootLength = Math.floor(canvas.height / columnWidth) * 2; // Increase root length for more space between roots
    let roots = generateRoots(rootLength, goldenRatio);

    function generateRoots(length, ratio) {
        const roots = [];
        let a = 1, b = 1;
        for (let i = 0; i < length; i++) {
            roots.push(Math.floor(a));
            const temp = b;
            b = a;
            a += temp * ratio;
        }
        return roots;
    }

    function draw() {
        context.fillStyle = '#000';
        context.fillRect(0, 0, canvas.width, canvas.height);

        for (let i = 0; i < columns; i++) {
            const x = i * columnWidth + columnWidth / 2; // Add columnWidth / 2 for center alignment
            let y = canvas.height - Math.floor(Math.random() * 10); // Randomly move up the roots
            for (let j = 0; j < roots.length; j++) {
                const noise = Math.random() * 5 - 2.5;
                const hue = Math.random() * 360;
                context.fillStyle = `hsl(${hue}, 100%, 50%)`;
                context.fillText(roots[j], x, y + noise);
                y -= columnWidth;
            }
            roots.pop();
            roots.unshift(Math.floor(roots[0] + roots[1] * goldenRatio));
        }
    }

    setInterval(draw, 369);

</script>
</body>
<div>
<br>
<li>See post about these rainbow domain name roots at <a href="https://innerinetcompany.com/2023/03/26/text-to-code-cyber-matrix-roots/">innerinetcompany.com/</a></li>
<li><a href="https://handshake.org/">Handshake.org/</a>Grow and Own The Roots of The Internet!</li>


- shout out to AgentSmith for this awesome Handshake logo!


<img src="https://user-images.githubusercontent.com/37987346/92327937-34e67580-f02b-11ea-9b64-22ce08cd6413.png">
</html>	
