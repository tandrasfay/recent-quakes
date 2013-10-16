Assignment Due: Monday, October 21st, 2013 (2013-10-21) at 11:59pm. On
Tuesday Oct 22nd in class we will **not** have a formal presentation.
Instead we will conduct a code review together.

To run this example you'll need to install the following packages
inside your virtual machine:

    sudo apt-get install libgeos-3.3.3 python-mpltoolkits.basemap python-mpltoolkits.basemap-data python-mpltoolkits.basemap-doc

Then run the notebook from your machine with this command:

    ipython notebook --no-browser --ip=0.0.0.0 --script --pylab=inline &

This assignment features two main roles: the Data Curator and the
Visualizer. All 4 members of your vertical group should work together
no matter what individual roles you have assigned.

You'll find me in our class IRC channel at times, but if you wish to
schedule either virtual or in-person time with me, then send me a bCal
invite.

If you schedule time with me you are welcome to work on the problem in
my office with the pair programming stations that I have available and
to ask me questions if that would help.

Your task:

Data Curation
-------------

The USGS data file we are using has been deprecated. You need to
upgrade this program to use the new USGS data feed:

http://earthquake.usgs.gov/earthquakes/feed/

Use the [Programmatic
Access](http://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php)
link and the [pandas JSON
parser](http://pandas.pydata.org/pandas-docs/dev/io.html) to access
the data.

You will also need to find a way to cache the data locally so that
your runs are exactly reproducible since the live data gets updated in
real-time. How can we have a program which can use the live data, but
also optionally can store data from previous runs so that we can
re-run the program in either mode: cached data or live data. Start
simple, keep the data isolated/separate from the source code, and
remember that the goal is to make it reproducible by someone else.

Visualization
-------------

The definition of `plot_ak()` has a *very bad code smell*! What if we
want to plot the earthquakes in California where I live now instead of
in my home state of Alaska? Can you spot the *code smell*? How can you
fix it so that given any arbitrary list of earthquakes you can plot
the bounding box around the location (e.g. the whole state) where the
quakes occured?

Also plot the quakes so we can see the magnitude and depth of each dot
instead of the way they are plotted now which only shows the location;
all the dots are the same color and the same size, but could be varied
to represent more information in the same amount of space.
