Requirements
====

* gnuplot

$ brew install gnuplot

* python 2.7.2

Use pythonbrew to manage your python versions.

$ script/bootstrap

## TroubleShooting

`set terminal aqua enhanced ...unknown terminal type`

You should install AquaTerm first, and then install gnuplot.

[Download AquaTerm](http://aquaterm.sourceforge.net/)

You double click a dmg file to install AquaTerm, maybe your installation
do not create the correct symlinks in `/usr/local/lib` because of no root
previlieges. So `brew install gnuplot --aquaterm` can not find it.
So you should do the following first:

```
sudo ln -s /Library/Frameworks/AquaTerm.framework/Versions/A/AquaTerm /usr/local/lib/libaquaterm.dylib
sudo ln -s /Library/Frameworks/AquaTerm.framework/Versions/A/AquaTerm /usr/local/lib/libaquaterm.1.0.0.dylib
sudo ln -s /Library/Frameworks/AquaTerm.framework/Versions/A/Headers/* /usr/local/include/aquaterm/.
```

Then check it:

```
ls /usr/local/lib/libaquaterm*
ls /usr/local/include/aquaterm/*
```

At last, you can reinstall gnuplot:

`$ brew install gnuplot --aquaterm`

Ok, when you run `set term` in gnuplot command line, you can see `aqua`.
