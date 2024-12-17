[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Sciter 鑴氭湰璋冪敤鏈湴鍑芥暟

```aardio aardio
//Canvas
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 鑴氭湰璋冪敤鏈湴鍑芥暟";right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

sciter.html = /**
<html>
<body style="background:black">
<canvas id="myCanvas" width="800" height="600" />

<script>

function line(particle, particle2) {
  context.beginPath();
  context.moveTo(particle.x, particle.y);
  context.lineTo(particle2.x, particle2.y);
  context.stroke();
}

function animate() {
  context.clearRect(0, 0, canvas.width, canvas.height);
  for (let i = 0; i < maxParticles; i++) {
    let particle = particles[i];
    context.fillRect(particle.x - particleSize / 2, particle.y - particleSize / 2, particleSize, particleSize);
    for (let j = 0; j < maxParticles; j++) {
      if (i != j) {
        let particle2 = particles[j];
        let distanceX = Math.abs(particle.x - particle2.x);
        let distanceY = Math.abs(particle.y - particle2.y);
        if (distanceX < threshold && distanceY < threshold) {
          context.lineWidth = ((threshold * 2) - (distanceX + distanceY)) / 50;
          let color = 200 - Math.floor(distanceX + distanceY);
          context.strokeStyle = 'rgb(' + color + ',' + color + ',' + color + ')';
          line(particle, particle2);
        }
      }
    }
    particle.x = particle.x + particle.vx;
    particle.y = particle.y + particle.vy;
    if (particle.x > canvas.width - particleSize || particle.x < particleSize)
      particle.vx = -particle.vx;
    if (particle.y > canvas.height - particleSize || particle.y < particleSize)
      particle.vy = -particle.vy;
  }
  requestAnimationFrame(animate);
}

let canvas = document.getElementById('myCanvas');
let context = canvas.getContext('2d');
let particles = [];
let particleSize = 4;
let maxParticles = 40;
let threshold = 100;
for (let i = 0; i < maxParticles; i++) {
  let particle = {
    x: Math.random() * canvas.width,
    y: Math.random() * canvas.height,
    vx: Math.random(),
    vy: Math.random()
  }
  particles.push(particle);
}
context.fillStyle = 'white';
animate();

</script>
</body>
</html>
**/

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/canvas.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/canvas.md')

