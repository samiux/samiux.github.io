|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# AMD Ryzen 4000 series CPU OpenGL in Firefox 106.0.5 and Ubuntu 22.04.1 LTS

OpenGL is not supported by default for firefox in Ubuntu 22.04.1 LTS.  You are required to set it up.  If you perfer newest Mesa display driver, you can install the PPA version.

Install :

```
sudo add-apt-repository -y ppa:netext/mesa-ryzen-stable
sudo apt update
sudo ./update_ubuntu
```

Uninstall :

```
sudo apt install ppa-purge
sudo ppa-purge ppa:netext/mesa-ryzen-stable
```

Add the following to ```/etc/environment```, after the setting, you need to reboot your box :

```
LIBVA_DRIVER_NAME=radeonsi
CLUTTER_PAINT=disable-dynamic-max-render-time
GST_VAAPI_ALL_DRIVERS=1
LIBGL_ALWAYS_INDIRECT=1
MOZ_X11_EGL=1
MOZ_ENABLE_WAYLAND=1
```

<!---At firefox, type ```about:config``` to toggle the following settings :

```
gfx.webgpu.force-enabled ---> true
gfx.webrender.all ---> true
gfx.x11-egl.force-enabled ---> true
webgl.disable ---> false
webgl.force-enabled → true
webgl.enable-ahardwarebuffer ---> true
webgl.auto-flush.gl ---> true

media.ffmpeg.vaapi.enabled ---> true
media.ffvpx.enabled ---> false
media.rdd-vpx.enabled ---> false
media.navigator.mediadatadecoder_vpx_enabled ---> true
```--->

For better performance, you can toggle the following settings :

```
browser.cache.disk.enable ---> false
browser.cache.memory.enable ---> true
browser.cache.memory.capacity ---> 1048576  
browser.sessionstore.interval ---> 15000000
```

Now, your web based videos will be played in firefox with lesser CPU resources.  

Samiux    
OSCE  OSCP  OSWP    
November 6, 2022, Hong Kong, China    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

