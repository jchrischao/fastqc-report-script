# fastqc-report-script

fastqc_v3.py ReadMe Documentation:

This Python script is designed to run FastQC, a quality control tool for high throughput sequence data, on a set of fastq files and generate a summary report. 

The script uses the FastQC program installed on the user's computer and requires the following packages to be installed: os, pandas, termcolor, openpyxl.

How the Script works:

The script is divided into several main parts:

1.	Defining file paths: The user must specify the path to the FastQC program, the input directory containing the fastq files to be analyzed, and the output directory where the FastQC output files will be saved.

2.	Running FastQC: The script iterates over all files in the input directory and runs FastQC on each file. If the file is compressed in .gz format, the script unzips it before running FastQC. After the analysis is complete, the script removes the .zip files generated by FastQC.

3.	Generating a summary table: The script extracts data from the summary.txt files generated by FastQC and creates a summary table in pandas DataFrame format. The table contains information on each sample's quality metrics, such as the total number of reads, the percentage of reads passing quality thresholds, and the overall quality score.

4.	Creating an Excel report: The script creates an Excel workbook and writes the summary table to the worksheet. The script applies cell highlighting to highlight the pass/fail/warning status of each metric. The script also merges and formats the header row and adjusts column widths to make the report more readable.

Usage:

To use the script, the user should modify the file paths as needed and run the script from the command line or an IDE. The output report will be saved in the report directory specified in the script. The user can open the report in Microsoft Excel or a compatible spreadsheet program to view the quality metrics for each sample.

1.	Install FastQC[these instructions are for macOS, please refer to site for PC installation]: 
a.	Go to the FastQC website and download the Mac version of the FastQC program. The downloaded file will be a .zip file.

b.	Extract the FastQC program: Open the .zip file and extract the FastQC program to a desired location on your Mac. For example, you can extract the program to your "Applications" folder.

c.	Make the FastQC program executable: Open a terminal window and navigate to the directory where you extracted the FastQC program. Use the following command to make the FastQC program executable:

Terminal:
chmod +x fastqc 

d.	Install Java: FastQC requires Java to run. If you do not already have Java installed on your Mac, you can download and install the latest version from the Java website.

e.	Test the installation: To test that FastQC has been installed correctly, open a terminal window and navigate to the directory where you extracted the FastQC program. Use the following command to run FastQC on a test fastq file:

Terminal:
./fastqc test.fastq 

f.	If FastQC runs successfully, it will generate a report file named "test_fastqc.html" in the same directory as the input fastq file. You can open the report file in a web browser to view the quality metrics for the input file. If you encounter any errors, refer to the FastQC documentation or the FastQC support forum for help.

2.	Install required packages for fastqc_v3.py script:
Open a terminal or command prompt and run the following command to install the required packages:

Terminal:
pip install pandas termcolor openpyxl

3.	Modify the file paths: Open the script in a text editor and modify the file paths as needed. The user must specify the path to the FastQC program, the input directory containing the fastq files to be analyzed, the output directory where the FastQC output files will be saved, and the report directory where the Excel report will be saved.

Examples:
# Define the path to the FastQC program
fastqc_path = "/Users/chrischao/FastQC/fastqc"

# Define the path to the input directory containing the fastq files to be analyzed
fastq_dir = "/Users/chrischao/Desktop/MiSeqResults/fastqc/fastqc_input"

# Define the path to the output directory where the FastQC output files will be saved
output_dir = "/Users/chrischao/Desktop/MiSeqResults/fastqc/fastqc_output/"

# Define the path to the report directory where the Excel report will be saved
report_dir = "/Users/chrischao/Desktop/MiSeqResults/fastqc/fastqc_reports"

4.	Run the script: Open a terminal or command prompt and navigate to the directory containing the script. Run the following command to execute the script:
Terminal:
python fastqc_v3.py 

5.	View the report: Open the Excel report located in the report directory specified in the script to view the quality metrics for each sample.




![image](https://github.com/jchrischao/fastqc-report-script/assets/76178310/4a46aeb0-3fb4-45cf-90fa-2f0e802810ef)
