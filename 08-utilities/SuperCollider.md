cmd b (server)
cmd enter (linea)
cmd . (stop todo)
	si quiero frenar por linea, hay que asignarlo a una variable cada uno
cmd d (help)

//this is a comment
/* this is also a comment */

(  )  //most often, for grouping expressions together
{  }  //function (package up some reusable functionality)
[  ]  //array (list of data)

---
2+2   //run me by the evaluate code key command with the cursor anywhere on this line - a four should appear in the posting window 

```js
{Pan2.ar(SinOsc.ar(440,0,0.1),0.0)}.play //similarly, concert A sine (works only if server booted)
```

```js
{Pan2.ar(SinOsc.ar(MouseX.kr(440,880),0,0.1),0.0)}.play
```

```js
2.postln;

Post << [2,3,4,5] <<nl; 
```

## Ugens
### Osc
SinOsc (mul es amplitud **1 100%** y add un agregrado)
Saw
Pulse
LFTri

### Ruido
WhiteNoise
PinkNoise

## Métodos
.ar (audio)
.kr (control)

```js
{SinOsc.ar(200,0,0.25,0)}.play
{Saw.ar(200,0.2)}.play
{SinOsc.ar(400,0,0.25,0)}.play
```
  
## Variables
### Locales
```js
(
{var freq, amp= 0.7;
 freq= 50;
 Saw.ar(freq,amp)!2}.play;
)
```
### Globales
a = 10;
~pep = 2;

```js
(
a = {Pulse.ar (20, 0.5, 0.3)!2}.play (fadeTime: 3);
b = {Saw.ar(30,0.1)!2}.play;
~ruido={PinkNoise.ar (0.2)!1}.play;
)

a.release(4);
b.release(2);
~ruido.release(3);
```
## Entradas
### Mouse
MouseX.kr
MouseY
MouseButton

```js
({var freq, amp= MouseY.kr(0, 0.7);
	freq= MouseX.kr(10,100);
 Saw.ar(freq,amp)!2}.play;
)
```

```js
({var freq, amp= SinOsc.kr (MouseY.kr(10, 200),0, MouseButton.kr(0,0.7));
	freq= MouseX.kr(10,100);
 Saw.ar(freq,amp)!2}.play;
)
```

### Secuencia

  ```js
(
r = Routine{
a = {Pulse.ar (20, 0.5, 0.3)!2}.play (fadeTime: 3);
	1.wait;
b = {Saw.ar(30,0.1)!2}.play;
	2.wait;
~ruido={PinkNoise.ar (0.2)!1}.play;
	4.wait;

a.release(4);
b.release(2);
~ruido.release(3);
	
}
)

r.play
// r.reset.play //para repetir
```

## Web
https://github.com/crucialfelix/supercolliderjs/
(cliente js)

https://www.sciss.de/temp/scalacollider.js/ (sc online??)
https://www.sciss.de/temp/scsynth.wasm/ (sc online??)


