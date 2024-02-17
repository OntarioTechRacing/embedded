# MATLAB Git Version Control Setup

The following documentation details how to set up git based version control for
MATLAB.

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Official Documentation](#1-official-documentation)

</details>

---

## 1 Official Documentation

From [MathWorks Help Center: Set Up Git Source Control](https://www.mathworks.com/help/simulink/ug/set-up-git-source-control.html):

- This is the main required step for setting up Git for MATLAB according to
  their documentation.

> If you use third-party source control tools, you must register your MATLAB and
> Simulink file extensions such as .mlx, .mat, .fig, .mlapp, .mdl, .slx, .mdlp,
> .slxp, .sldd, and .p as binary formats. Also register extensions for MEX
> files, such as .mexa64, .mexmaci64, .mexmaca64, and .mexw64. If you do not
> register the extensions, these tools can corrupt your files when you submit
> them by changing end-of-line characters, expanding tokens, substituting
> keywords, or attempting to automerge. Corruption can occur if you use the
> source control tools outside of MATLAB or if you try submitting files from
> MATLAB without first registering your file formats. Also check that other file
> extensions are registered as binary to avoid corruption at check-in. Check and
> register file extensions such as .xlsx, .jpg, .pdf, .docx, and so on. To
> register your binary file extensions with Git, add them to a .gitattributes
> file. If you create a new project that uses Git source control or switch an
> existing project from another source control system to Git source control,
> MATLAB automatically creates a .gitattributes file and populates it with a
> list of common binary files to register. If a .gitattributes file is not
> automatically created, you can create one that contains the list of common
> binary files to register. In the MATLAB Command Window, enter:
> ```
> copyfile(fullfile(matlabroot,'toolbox','shared','cmlink','git','auxiliary_files','mwgitattributes'),fullfile(pwd,'.gitattributes'))
> ```
