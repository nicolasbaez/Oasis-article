# Oasis-article
Two oceans of time, just a moment

![buh](https://github.com/nicolasbaez/Oasis-article/blob/main/xp034.gif)
```javascript
h = 255;
k = 0;
n = h * 2;
x = [];
y = [];
z = [];
setup = (_) => {
  r = (x) => random(x);
  createCanvas(n, n, WEBGL);
  for (i = 0; i < n; i++) {
    a = map(i, 0, n, -h, h);
    x[i] = r(a);
    y[i] = r(a);
    z[i] = r(a);
  }
};
draw = (_) => {
  background(r(h));
  rotateX(k);
  noFill();
  beginShape();
  for (i in x) vertex(x[i], y[i], z[i]);
  endShape();
  k += 0.01;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp034.gif", 628, { delay: 0, units: "frames" });
  }
};
