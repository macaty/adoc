[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Sciter 脚本调用本地函数

```aardio aardio
//Canvas
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 脚本调用本地函数";right=1014;bottom=523;)
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

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/canvas.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/canvas.md')
