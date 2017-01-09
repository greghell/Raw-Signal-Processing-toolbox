# Raw-Signal-Processing-toolbox

****  channel_spec.cc  ****
Returns the power spectral density of pol1 and pol2 estimated over a complete RAW file (all data blocs) for a chosen coarse channel.

Call:
spec = channel_spec(str_file, nChan, nResol, nOverlap, nWin, nWinParam);
str_file : character string to the RAW file
nChan : Number of coarse channel to be analyzed
nResol : number of frequency points over which the signal will be analyzed - will be modified to the closest power of 2.
nOverlap : number of overlapping windows staring over a nResol-long time window (uniformly spread)
nWin : window number (see win_apod.c)
nWinParam : parameter of the window chosen (not always relevant)
spec : 2 first columns are PSD of pol#1 and pol#2. 3rf column is frequency axis. 4th column is window.

****  fft.c  ****
Performs a Fast Fourier Transform, called in:
channel_spec.cc
read_2_bits.cc

****  raw_info.cc  ****
Displays information about a RAW file

****  read_2_bits.cc  ****
Returns the power spectral density of pol1 and pol2 estimated over a single data bloc for a chosen coarse channel.

Call:
spec = channel_spec(str_file, nChan, nBloc, nResol, nOverlap, nWin, nWinParam);
str_file : character string to the RAW file
nChan : Number of coarse channel to be analyzed
nBloc : Data bloc number
nResol : number of frequency points over which the signal will be analyzed - will be modified to the closest power of 2.
nOverlap : number of overlapping windows staring over a nResol-long time window (uniformly spread)
nWin : window number (see win_apod.c)
nWinParam : parameter of the window chosen (not always relevant)
spec : 2 first columns are PSD of pol#1 and pol#2. 3rf column is frequency axis. 4th column is window.

****  win_apod.c  ****
Returns an apodization window. The following windows are currently available:
Rectangular
Bartlett
Hanning
Gaussian (include parameter < 0.5)
Blackman-Harris (include parameter < 0.16)
