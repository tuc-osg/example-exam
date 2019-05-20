# Exam class for the TUC Operating System Group

This is the template for our exams, which relies on the [LaTex exam class](https://www.ctan.org/pkg/exam). It supports:

  - Useful defaults for layout and titlepage
  - Automated generation of personalized exams from a list of students.
  - Automated handling of multilangual exams
  - Flexible directory layout for source and output documents
  
  In addition, there are Python scripts for:
  - Generation of a seating plan, based on predefined room capacities.
  - Generation of a checklist for students showing up.
  - Generation of grading proposals based on ECTS.

This is still work in progress.

## Installation

- Make sure you have Python 3 and LuaLaTeX installed.
- *pip3 install openpyxl*
- LaTeX:
  - clone this repo to a folder, e.g. `git clone git@github.com:tuc-osg/osg-exam.git ~/Documents`
  - prepare a folder for the local tex tree: `mkdir -p $(kpsewhich -var-value=TEXMFHOME)/tex`
  - link the class subfolder to that directory: `ln -s ~/Documents/osg-exam/osgexam $(kpsewhich -var-value=TEXMFHOME)/tex/osgexam`
  - if necessary, run `sudo texhash` if the class isn't found.
- You can get an update with `git pull` inside your local repository (`~/Documents/osg-exam`)

## Usage

- Create a new latex document with the osgexam class and set the option "development"
- Run *lualatex -shell-escape <source.tex>* 
   - Alternatively: copy *latexmkrc* into your directory and run *latexmkrc <source.tex>*  
- For interactive mode, comment out *development* option

## Rules
- In <exam>.xlsx, the following format must be kept:
  - All data is on the first sheet.
  - There are columns with the name "Matrikelnummer", "Vorname" and "Name" and possibly "Platz" (not case sensitive)
  - There are no empty rows.
