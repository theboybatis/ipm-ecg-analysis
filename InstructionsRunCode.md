#How to run the software.

# Introduction #

The java code reads two text files.
The first text file lists the name of the output file and the list of txt files containing the ECG data.
This txt file is named egg\_header.txt

The second txt file read contains the ECG signal. The code only reads the first column of this txt file
The ECG signal has to be centered (i.e. zero mean) and should preferably represent the ECG value in mV.

The code is written to work at 256Hz, but could work at 250Hz. The sampling frequency is set on line 50 of QRSDetector.java (private int samplingFrequency = 256;)

The string variable indicating the code directory and the data directory have to be changed by the user in order to suit his settings:
line 30 of QRSDetector.java 	private String root\_dir="/Users/julian/Documents/Work/EclipseWorkspace/QrsDetector/";
and
line32 and 33 of MIT\_QrsDetector\_Runner.java
> String root\_dir="/Users/julian/Documents/Work/EclipseWorkspace/QrsDetector/";
> String data\_dir= "/Users/julian/Documents/Matlab/";


# Details #
line 1047 of QRSDetector.java has to be changed if ECG sample is not written in the first column
> //only read the first column of the txt file
> StringTokenizer tok = new StringTokenizer (strLineFile, " ");
> sample = Double.parseDouble(tok.nextToken());