
<!-- ABOUT THE PROJECT -->
## About The Project

This is Team CVP's solution to [NIH NCAT's Bias Detection Tools in HealthCare Challenge]( https://expeditionhacks.com/bias-detection-healthcare/)

### Architecture
![AI Bias Tool Architecture](https://github.com/cvp-bias-detection-healthcare/cvp-bias-detection-healthcare.github.io/blob/e32af3038ab9d87ac031e5171713adff2145dd73/assets/img/23-003-001-02_NCATS%20AI%20Challenge-02.png)


<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.


### Prerequisites

* Python 3.8
* Requirments are in `scripts\requirements.txt`


### Folder Structure
The script is using the following directory tree structure:
```/
├── scripts/           # This is where `measure_disparity.py` and `mitigate_disparity.py` are
├── reports/           # Location for the html report generated by the script
├── input_model/       # Insert input model data here
├── output_model/      # This is where the mitigated model prediction is saved
├── data/              # Sample data to run the model 
├── js/                # javascript for the team submission landing page 
├── css/               # css files for the team submission landing page 
├── assets/            # images for the team submission landing page 
```


### Installation
The only technical requirements before running are a Python environment setup on the computer and a Git client to retrieve the code, <br />
though you could download our code from GitHub’s website if the latter is problematic. We recommend Anaconda which has setup directions here.  <br />
CPU, RAM, and storage requirements are dependent on the size of the dataset you wish to measure and mitigate bias on. You should generally have <br />
RAM that is greater than or equal to the dataset. <br />
<br />
Once Python is available and an environment is activated:
<br />
<ol>
  <li> Run “Git clone https://github.com/cvp-bias-detection-healthcare/cvp-bias-detection-healthcare.github.io” </li>
  <li> Run “pip install requirements.txt” </li>
 </ol>
<br />

**To use the measure_disparity.py file:**  <br />
1.	Open “measure_disparity.py”, located in the scripts folder, in a text editor. <br />
2.	The first 15 lines of code are used for storing metadata about your dataset of interest. Please modify them as needed to locate the data, tag the protected <br /> features, and label which columns have the probabilities, the true labels and sample weights. Save your changes. <br />
3.	Run “python measure_disparity.py”. An HTML report (“measure_rerport.html”) will be automatically generated in the “reports” folder <br />
4.	Double click it or transfer to a computer with an internet connected web browser to review it. <br />
<br />

**To use the mitigate_disparity.py file:**
1.	As required by the challenge, the mitigate script returns a Python object/class with fit(), transform(), and predict() methods in addition to a measure() method for report generation. Read the README inline comments for the class creation instance and class methods to understand the arguments and parameters they need as input
2.	The “mitigate_disparity.py” file needs to be imported as a module in another notebook or a .py script.
3.	For ease of use, we have included a “run_mitigate.ipynb” sample notebook which is setup to use the object and its methods to perform a full mitigation
4.	You may run this notebook as is with our sample data file (“diabetes_data”) or copy its contents for use with your own dataset
5.	For the latter, you will need to define your train and test pandas dataframes 
6.	We recommend predefining all of the critical fields (like in the measure script) that need be passed into the class and methods
7.	For this script, the LightGBM model parameters dictionary is another critical field, and you can either keep it as is or modify as you see fit for your dataset
8.	Once all required parameter inputs are defined, initialize the Mitigator object and call its methods in this order: transform(), fit(), predict(), measure(). These together will generate the “imbalance_report.html” and the “mitigate_report.html” (same format analysis as “measure_report.html”) in the reports folder. It also outputs the transformed train dataset, the predicted test dataset, and the threshold tuned predicted test dataset to help build an audit trail.
<br />
For more detailed information on how the mitigation process works, please reference the code comments in the GitHub code.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the BSD 3 License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

* Manpreet Khural - manpreetkhural@cvpcorp.com
* Cal Zemelman - calzemelman@cvpcorp.com
* Lauren Winstead - laurenwinstead@cvpcorp.com
* Wei Chien - weichien@cvpcorp.com
* Rose Anderson - roseanderson@cvpcorp.com


Project Link: [https://github.com/cvp-bias-detection-healthcare/](https://github.com/cvp-bias-detection-healthcare/cvp-bias-detection-healthcare.github.io/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
