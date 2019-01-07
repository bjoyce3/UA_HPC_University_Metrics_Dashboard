# UA_HPC_University_Metrics_Dashboard
A repository to create an automatic dashboard for [Higher Education Research and Development Survey (HERD)](https://www.nsf.gov/statistics/srvyherd/), [The Integrated Postsecondary Education Data System (IPEDS)](https://nces.ed.gov/ipeds/), and University of Arizona-specific metrics. 

## Project Requirements
Engineers write these all the time. They've got a good way of thinking about projects. Sometimes it's good to think like an engineer; sometimes it's good to think like a scientist. Here's my best shot at the former.

### Functional Requirements
1. Data Import and Cleanup
    - Input data products needs to not be sacred
      - Shouldn't have to have access to special cleaned up data source to run the dashboard
      - No special permissions are required for accessing the public data (IPEDS and HERD)
      - 
2. Data Analysis
3. Visualization and Dashboard
4. Consuming the final project
    - Stakeholders should be able to access the dashboard easily
      - No command line calls
      - Login would be fine
      - Always available but not necessarily always on
    - Data should be easy to understand, play with, ask questions, and investigate
      - Widgets with drop down to change information displayed
      - Access to raw data (and output/download would be phenomenal)
    - Responsive and robust enough to live demonstrate during talks or workshops

### Technical Requirements
1. All data must be pulled from the original databases (i.e. HERD, IPEDS, etc)
  - Cleanup of data is scripted
  

# How to Setup This Project From Scratch
1. Exosphere
2. Setup on Ubuntu 18.04 cloud computer
    - `tmux`
    - `wget` and `tmux` were already installed
    - Setting up Redash using the Redash Docker image `wget https://raw.githubusercontent.com/getredash/redash/master/setup/setup.sh`
      - Above command also sets up Docker and other dependencies from scratch/blank computer
    - `chmod +x setup.sh`
    - `./setup.sh`
    - `echo 'export PATH=$PATH:/usr/local/bin' >> .bashrc`
    - Setup a nested tmux session while in the docker group `sudo su - exouser` 
      - `groups` can be used to check the groups you're in
      - Should see docker listed as one of the groups
    - `cd /opt/redash/`
    - `docker-compose ps`
      - Lists running docker containers (redash runs several to setup from script above)
      - Should see 7 images running
    - Redash didn't setup a secure connection from the above setup.sh script
      - Setup Domain name using freemyip.com
        - Check out secrets file for token and other details
        - Need to redo if want to change domain name
      - Pointed the domain name at the IP address
        - Need to rerun curl command from exosphere VM if IP address changes
      - Stopped nginx container running from Redash docker-compose file
      - Created a /opt/caddy directory
      - Changed ownership to exouser
      - Created a Caddyfile inside (view in raw mode to see actual structure of Caddyfile)
                ```
                ua-metrics.freemyip.com  
                proxy / 127.0.0.1:5000 {   
                        transparent  
                }  
                ```
      - Started caddy in it's own tmux pane
    - Setup Python 3 `sudo apt install python3-pip`
    - Setup csv-to-sqlite `pip3 install csv-to-sqlite`
3. Setup Data
  1. Pull data using `wget`
  2. Clean up data using `pandas` script
    - Original data from HERD and IPEDS is extremely messy
      - Breaks import into SQLite because HERD has blank columns (for looks apparently :|)
      - 
  3. Import into SQLite
    - 

## Jupyter Notebooks
- All Jupyter notebooks are available in this repository as [Git Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
   - Newer versions of the submodule notebooks (and other code) may be available on [Chris Deer](https://github.com/CGDeer/HERD_Analysis.git) and [Cynthia Hart's](https://github.com/cbresloff/IPEDS_DATA.git) subrepositories
   - These submodules are pulled here based on Git commit hashes

# Project Design and Execution
- Initial coding and data cleaning efforts were committed to GitHub Repos of [Cynthia Hart](https://github.com/cbresloff/IPEDS_DATA.git) and [Chris Deer](https://github.com/CGDeer/HERD_Analysis.git). 


# Interesting Observations
There's always a few in data science projects. Here's some of the things we saw in no particular order.

