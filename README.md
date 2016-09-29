# TriLinSpeed.exe 

A win32 benchmarking program for single threaded processor compute speed

copyright (C) <2000>  <M. A. Chatterjee>  <deftio [at] deftio [dot] com>
version 0.1 M. A. Chatterjee
 
## About TriLinSpeed

TriLinSpeed.exe is a computational benchmark written C++ to test sustained single threaded integer and floating point benchmarks under Microsoft Windows computers.  It works by creating a very large virtual 3D image and then computing millions of 3D linear interpolations on that image over a psuedo random (but fixed) sequence of points with a fixed time interval.  By design, the image was set larger than the CPU cache so that cache effects would be minimized.  Windows 32 bit platforms provide a function which measures processor time used only when an app is active and this was used for the timing aspect of the measurement.

## History and Purpose

It was written for assessing relative processor speeds possible for the Windoscope graphics rendering engine (Windoscope was a company founded in 1998 to do medical image analysis).  At that time Pentium 166MHz processors were common and the Pentium Pro and Pentium II processors were just coming to market.  To assess how much performance the graphics engine would likely show under certain CPU and memory configurations this benchmark was created as a crude platform asssessment.  

## Notes

* Simple Console App which dumps a single file trilin.txt with the integer and floating point speeds measured.
* Relatively insensitive to other apps running, however if memory is very full, then virtual memory access will cause lower scores
* Fairly stable results (given that is hasn't been recompiled since 2000 for consistency) across:
	* Win2k, WinMe, WinXP, Win Vista, Win 7 32bit, Win7 64bit, Win8 64bit, Win10 64bit
	* can also run under wine on Linux
	* Pentium, Pentium MMX, Pentium II, Pentium III, Pentium 4, Intel Core series, AMD 32 and 64 bit processors
* Only measures single threaded throughput
* compiled under Visual Studio 6.0 (C++)

## Running and Example Output
The following text is written to a file trilin.txt in the current working directory and is also echoed to console if running from commandline.

```
Trilin Speed Test
million trilin interps per sec (fix) =   88.3011
million trilin interps per sec (float) = 6.35501
```

Note that double clicking on the app will run it and leave the above mentioned file after a few seconds.  Some versions of Windows will complain that the app is unsigned (which is true) however it was written before app signing was matured on the Windows platform.

The numbers are somewhat arbitrary and is more meant for relative platform comparison.  Note that integer benchmark is called "fix" since integer calcs are done with fixed-point math.

### Other OSes
TriLinSpeed.exe can also be run under wine but there is no port at this time to other OSes.  A challenge with porting an old benchmark like this is that compiler and OS differences can affect the measurement.

## Represenative Benchmarks with TriLinSpeed.exe

| Model         | OS                               | Processor           | Core Clock | RAM   | Trilin Integer | Trilin Float |
|---------------|----------------------------------|---------------------|------------|-------|----------------|--------------|
| Solo 9100     | Win 2K                           | Intel Pentium II    | 0.4GHz     | 192MB |  3.6           | 0.4          |
| Custom        | Win XP Pro                       | Intel Pentium 4     | 2.4GHz     | 512MB | 15.2           | 1.5          |
| Inspiron 6000 | Win XP Pro                       | Intel Pentium M     | 2.1GHz     | 1.5GB | 29.4           | 2.5          |
| Inspiron 600m | Win XP Pro                       | Intel Pentium M     | 1.7GHz     | 1.5GB | 24.2           | 2.1          |
| Thinkpad X61  | Win XP Home                      | Intel Core 2 Duo    | 2.0GHz     | 2GB   | 39             | 3.4          |
| Thinkpad X61  | Ubuntu 12.10-i386 Studio+wine1.5 | Intel Core 2 Duo    | 2.0GHz     | 2GB   | 47             | 3.1          |
| Thinkpad T61p | Ubuntu 14.04-x64 LTS             | Intel Core 2 Duo    | 2.6GHz     | 4GB   | 64             | 4.7          |
| Thinkpad T410 | Win 7 Ultimate                   | Intel Core i5-520m  | 2.4GHz     | 8GB   | 50             | 6.0          |
| Thinkpad T410 | Ubuntu 14.04-x64 LTS+wine1.5     | Intel Core i5-520m  | 2.4GHz     | 8GB   | 60             | 6.1          |
| Thinkpad T510 | Win7-64 Pro                      | Intel Core i7-620m  | 2.7GHz     | 8GB   | 59             | 6.7          |
| LaVie Z       | Win10 Home (64 bit)              | Intel Core i7-5500U | 2.4GHz     | 8GB   | 82             | 5.9          |
| X1 Carbon     | Win10 Pro (64)                   | Intel Core i7-5600U | 2.6GHz     | 8GB   | 90             | 6.5          |

If you run the benchmark, find it useful and would like your results included here just email me with the above info.

## Source Code
Will be made available ... when I can find it.  ;( No guarantees it will be pretty.


## License
BSD 2-clause (see LICENSE.txt file)


