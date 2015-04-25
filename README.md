## Three.js as native application with electron

This examples is a example of three.js game as native application

- the idea came from @Nazariglez in this [tweet](https://twitter.com/Nazariglez/status/591915046151815169).
  A nice guy, be sure to check it out!

- i loved the idea and tried to reproduce it

- what is electron ?
  - this is the new name of *atom-shell*
  - it is all explained [in this post](http://blog.atom.io/2015/04/23/electron.html)
  - it is the 'plateform' under [atom editor](https://atom.io/) is running
  - to get more information, checkout [eletron's homepage](http://electron.atom.io/)3

- It short, it is an easy way to write desktop apps with web technology.

- Let's see what we can do with three.js :)


## How to do it
- before having a three.js native apps, you need to install electron
- it is all [electron's quick start](https://github.com/atom/electron/blob/master/docs/tutorial/quick-start.md)
- point it to another page, a three.js pages


## How to make this page transparent

To make it appear nicer, we can try to make the window background transparent and not display the window frame.
This will give a nice floating effect to the 3d.

###First modify this in electron main.js

```javascript
//mainWindow = new BrowserWindow({width: 800, height: 600});
mainWindow = new BrowserWindow({width: 800, height: 600, transparent: true, frame: false});
```

Second, be sure to make the body background transparent 

```css
body { 
  background-color: rgba(0,0,0,0);
}
```

Then tell three.js to stay transparent too

```javascript
renderer = new THREE.WebGLRenderer( { antialias: false, alpha : true } );
renderer.setClearColor(0x000000, 0);
```

Now everybody is transparent and you can see the 3d floating on top :)
