# Satellite Orbits
**********************************

Generally the software should read Navigation RINEX v3.x files to extract
orbit information. At this stage, its better to use multi-GNSS navigation files
to check and validate program behaviour.

To get multi-GNSS RINEX v3.x Navigation files, use any repository possible; for
example, CDDIS has its own repository with a nice [info page](https://cddis.nasa.gov/Data_and_Derived_Products/GNSS/RINEX_Version_3.html);
note that the correct folder is the `p` one, aka should you need navigation data 
for year 2020 and doy 50, just navigate to the year/doy/yr2p [folder](ftp://cddis.nasa.gov/gnss/data/daily/2020/050/20p/).
In there, you can also find the `brdc` file for the day, containing all SV 
messages of the day.

The library does not handle SP3 files, but the program [sp3py.py](../blob/master/var/sp3py.py)
does. You can use this progeam to extract SV position and satellite clock errors 
and then validate results from Navigation files.

It is a fairly straigh-forward program, easy to use:
```
sp3py.py -i ../data/COD0MGXFIN_20200010000_01D_05M_ORB.SP3 -s R12
## Ref System: IGS14, Time System GPS
"2020-01-01 00:00:00"  -21051.999666   +8279.338716  -11732.249093     +92.862104
"2020-01-01 00:05:00"  -21506.081482   +8386.938680  -10796.370697     +92.863237
"2020-01-01 00:10:00"  -21919.022140   +8499.341843   -9837.088202     +92.864158
"2020-01-01 00:15:00"  -22289.961141   +8614.540460   -8856.482603     +92.865172
"2020-01-01 00:20:00"  -22618.198098   +8730.488077   -7856.680951     +92.866270
"2020-01-01 00:25:00"  -22903.195363   +8845.110057   -6839.851703     +92.867294
"2020-01-01 00:30:00"  -23144.579929   +8956.314251   -5808.199949     +92.867983
"2020-01-01 00:35:00"  -23342.144565   +9062.001761   -4763.962592     +92.868949
"2020-01-01 00:40:00"  -23495.848207   +9160.077740   -3709.403433     +92.870025
"2020-01-01 00:45:00"  -23605.815574   +9248.462199   -2646.808221     +92.870992
"2020-01-01 00:50:00"  -23672.336045   +9325.100731   -1578.479644     +92.872144
"2020-01-01 00:55:00"  -23695.861776   +9387.975138    -506.732291     +92.873123
"2020-01-01 01:00:00"  -23677.005076   +9435.113890    +566.112397     +92.874162
....
```
The output can then be ploted against results from the project program files.

The RINEX v3.x Navigation files can be read via the test programs: [testNavRnxG.out](../blob/master/test/test_navrnx_G.cpp) 
(for GPS satellites) and [testNavRnxR.out](../blob/master/test/test_navrnx_R.cpp) (for 
GLONASS). Usage of the programs is simple:

```
testNavRnxR.out ../data/AQUI00ITA_R_20190500000_01D_MN.rnx 01
# Read 1 data blocks
# Last status was: 8
# Navigation frames for PRN1: 0
# First frame read for PRN=1; going on ...
"2019-02-18 08:46:18"        +10656.347856       +22662.029365        -4895.225250        +39.60542381
"2019-02-18 08:47:18"        +10642.527771       +22622.504354        -5103.619643        +39.60542381
"2019-02-18 08:48:18"        +10627.640154       +22581.583868        -5311.573099        +39.60542381
"2019-02-18 08:49:18"        +10611.673850       +22539.280049        -5519.067652        +39.60542381
"2019-02-18 08:50:18"        +10594.617881       +22495.605230        -5726.085375        +39.60542381
"2019-02-18 08:51:18"        +10576.461451       +22450.571930        -5932.608383        +39.60542381
"2019-02-18 08:52:18"        +10557.193951       +22404.192853        -6138.618833        +39.60542381
"2019-02-18 08:53:18"        +10536.804956       +22356.480888        -6344.098926        +39.60542381
"2019-02-18 08:54:18"        +10515.284230       +22307.449101        -6549.030909        +39.60542381
"2019-02-18 08:55:18"        +10492.621729       +22257.110736        -6753.397078        +39.60542381
"2019-02-18 08:56:18"        +10468.807604       +22205.479213        -6957.179775        +39.60542381
"2019-02-18 08:57:18"        +10443.832198       +22152.568123        -7160.361394        +39.60542381
...
``` 

Now to compare results, we can easily use a ploting tool, eg `gnuplot`
```
gnuplot
set xdata time
set timefmt '"%Y-%m-%d %H:%M:%S"'
plot "foobar1" u 1:2 w lp, "foobar2" u 1:2 w lp
```
