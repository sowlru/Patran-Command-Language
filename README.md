This folder contains Patran Command Language library (beam.plb). 
Library consist of 2 function: beam1D.pcl and beam2D.pcl.

To compile function beam1D.pcl into beam.plb:
1. Make sure that Patran & Nastran 2017.0.2 is installed.
2. Create working directory: C:\avk\test\patran
3. Move to this folder: Win+R-> cmd-> cd C:\avk\test\patran
4. Run Patran compiler: p3pclcomp
5. Create library: !!library create beam
6. Compile function: !!Input beam1D.pcl
7. Add function to library: !!compile beam1D beam
8. Check: !!library list beam - BEAM should appear
9. Add line in C:\appl\MSC\Patran_x64\20170\p3epilog.sys: !!library "C:\avk\test\patran\beam.plb" before ui_Write(...)

To run this function:
1. Put _run.bat in working folder and double click. This batch file run Patran and auto-delete old analysis files (t.*, *.ini, .jou, ..)
2. Enter beam(1., 1., 0.1, 10., 1) in command line in the bottom of Patran window.
3. Example analysis will run. 
4. Function parameters: beam(width, height, thk, length, mat_code). 
5. Cross-section used in this analysis: I-section.
6. Make sure that hand analysis result in Command Window is consistent with Patran analysis.
