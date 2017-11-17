# To get the PAMI15 version

```bash
git clone git@github.com:jvlmdr/tracker_benchmark.git
cd tracker_benchmark
git checkout pami15
```

# To set up the results of existing methods

```bash
mkdir -p tracker_benchmark/results/
cd tracker_benchmark/results/
wget http://cvlab.hanyang.ac.kr/tracker_benchmark/v1.1/pami15_TRE.zip
unzip pami15_TRE.zip
rm pami15_TRE.zip # Optional
```

# To download the sequences

```bash
cd tracker_benchmark/data/
rm -r bolt/
mkdir dl/
cd dl/
wget https://gist.githubusercontent.com/jvlmdr/00968b1cf9d1a0e57b8ed93fe158f224/raw/ab3717520db480496cbebb9b90482b08011734fa/download.sh
bash download.sh
cd ..
ls dl/*.zip | xargs -n 1 unzip
rm -r dl/ # Optional
```

In Matlab:

```matlab
addpath util;
run MakeSequenceConfigVer11;
```

# To plot the results

In Matlab:

```matlab
trackers = SetupTrackers();
sequences = ScanSequences();
PlotSuccessRates('pami15_TRE', 'ALL', trackers);
```

# To add a tracker
