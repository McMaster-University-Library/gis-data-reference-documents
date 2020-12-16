- use PuTTy scp to transfer a directory and all of its contents to a remote location
```pscp -P 22122 -r C:\Users\brodeujj\Downloads\omeka-themes\centerrow brodeujj@130.113.111.189/var/www/omeka-s/themes```

- copy a list of items to a new directory:  
```for %I in (1km17592047920SWOOP2015.img 1km17591047890SWOOP2015.img 1km17590047880SWOOP2015.img 1km17589047870SWOOP2015.img 1km17591047900SWOOP2015.img 1km17590047890SWOOP2015.img 1km17589047880SWOOP2015.img 1km17591047910SWOOP2015.img 1km17590047900SWOOP2015.img 1km17589047890SWOOP2015.img 1km17591047920SWOOP2015.img 1km17590047910SWOOP2015.img 1km17589047900SWOOP2015.img 1km17590047920SWOOP2015.img 1km17589047910SWOOP2015.img 1km17589047920SWOOP2015.img 1km17597047860SWOOP2015.img 1km17597047870SWOOP2015.img 1km17597047880SWOOP2015.img 1km17597047890SWOOP2015.img 1km17597047900SWOOP2015.img 1km17597047910SWOOP2015.img 1km17597047920SWOOP2015.img ...) do copy %I ALonsdale```

- Create a list of specific types of files in a directory with filenames only:  
```dir /a /b *.jpg >list.txt```
