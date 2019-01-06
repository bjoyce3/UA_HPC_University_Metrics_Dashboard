# UA_HPC_University_Metrics_Dashboard
A repository to create an automatic dashboard for [Higher Education Research and Development Survey (HERD)](https://www.nsf.gov/statistics/srvyherd/), [The Integrated Postsecondary Education Data System (IPEDS)](https://nces.ed.gov/ipeds/), and University of Arizona-specific metrics. 

## Project Requirements
Engineers write these all the time. They've got a good way of thinking about projects. Sometimes it's good to think like an engineer; sometimes it's good to think like a scientist. Here's my best shot at the former.

### Functional Requirements
1. Data Import and Cleanup 
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
  

# How to Run This Project

## Jupyter Notebooks
- All Jupyter notebooks are available in this repository as [Git Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
   - Newer versions of the submodule notebooks (and other code) may be available on [Chris Deer](https://github.com/CGDeer/HERD_Analysis.git) and [Cynthia Hart's](https://github.com/cbresloff/IPEDS_DATA.git) subrepositories
   - These submodules are pulled here based on Git commit hashes

# Project Design and Execution
- Initial coding and data cleaning efforts were committed to GitHub Repos of [Cynthia Hart](https://github.com/cbresloff/IPEDS_DATA.git) and [Chris Deer]((https://github.com/CGDeer/HERD_Analysis.git). 


# Interesting Observations
There's always a few in data science projects. Here's some of the things we saw in no particular order.

