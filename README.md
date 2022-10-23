# NCKU_CANS_RiverCPS
This is a project of a testbed to collect relevant data sets to support machine learning requirements, such as training models and analyzing attacks, etc.

Install mininet 2.3.0 (python 2)

```cli
git clone https://github.com/mininet/mininet

cd mininet
git tag  # list available versions
git checkout -b mininet-2.3.0 2.3.0  # or whatever version you wish to install
cd ..

sudo PYTHON=python3 mininet/util/install.sh -n   # install Python 3 Mininet

mininet/util/install.sh -h # look for anything you want to install

mininet/util/install.sh -v # don't forget to install Open vSwitch
```
Install minicps
```cli
sudo pip install minicps
# clone the 'python3' branch of minicps for the newest python3 version examples
git clone -b python3 --single-branch https://github.com/scy-phy/minicps.git 
cd minicps/examples/swat-s1 # test minicps with swat example
sudo python3 run.py
```
ImportError: No module named mininet.net 
-> Move mininet to /home -> go to swat-s1 directory -> export PYTHONPATH=$PYTHONPATH:$HOME/mininet
If swat-s1 is launched succesfully, you should see the following lines
```cli
*** Ping: testing ping reachability
attacker -> plc1 plc2 plc3 
plc1 -> attacker plc2 plc3 
plc2 -> attacker plc1 plc3 
plc3 -> attacker plc1 plc2 
*** Results: 0% dropped (12/12 received)
mininet> 
```
Then minicps is good to go !
