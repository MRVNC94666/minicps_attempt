# NCKU_CANS_minicps
This is a project of a testbed to collect relevant data sets to support machine learning requirements, such as training models and analyzing attacks, etc.

Install mininet 2.3.0 (python 3)

```
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
```
sudo pip install minicps
# clone the 'python3' branch of minicps for the newest python3 version examples
git clone -b python3 --single-branch https://github.com/scy-phy/minicps.git 
cd minicps/examples/swat-s1 # test minicps with swat example
sudo python3 run.py
```
ImportError: No module named mininet.net 
-> Move mininet to /home -> go to swat-s1 directory -> export PYTHONPATH=$PYTHONPATH:$HOME/mininet
If swat-s1 is launched succesfully, you should see the following lines
```
*** Ping: testing ping reachability
attacker -> plc1 plc2 plc3 
plc1 -> attacker plc2 plc3 
plc2 -> attacker plc1 plc3 
plc3 -> attacker plc1 plc2 
*** Results: 0% dropped (12/12 received)
mininet> 
```
Then minicps is good to go !

# Research history

22/10/23 11:40 Figure out how to set up environment on linux pc with python3. (Not using the vm ubuntu server version approach.) 
22/10/23 11:48 Open `minicps/examples/swat-s1/logs/README.md` while the swat example is running, the pc die.
22/10/23 15:10 Try to create a sqlite BD for swat-s1 with `sudo python3 init.py` in `~/minicps/examples/swat-s1`
22/10/23 15:20 Encounter an error says `SyntaxError: Missing parenthese in call to 'print'. Did you mean print('DEBUG set_query:',set_query)?`
22/10/23 15:30 Edit the `state.py` with `sudo gedit /usr/local/lib/python3.8/dist-packages/minicps/states.py`, complete every `print()` and `expect()` function. Then run `init.py` again.
22/10/23 17:30 Research stop due to the change of direction of my study. 
