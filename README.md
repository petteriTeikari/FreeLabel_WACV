# FreeLabel: A Publicly Available Annotation Tool based on Freehand Traces

Dias, Philipe Ambrozio, Zhou Shen, Amy Tabb, and Henry Medeiros. **"Freelabel: A publicly available annotation tool based on freehand traces."** In *2019 IEEE Winter Conference on Applications of Computer Vision (WACV)*, pp. 21-30. IEEE, 2019. https://doi.org/10.1109/WACV.2019.00010

This repository forked from https://bitbucket.org/phil_dias/freelabel-wacv/src/master/

## PETTERI: Instructions

### Prerequisites

1) Anaconda Python 3.x Individual Edition, https://www.anaconda.com/distribution/, e.g. download the [graphical macOS installer](https://docs.anaconda.com/anaconda/install/mac-os/)

### When you have the prerequisites done

#### Ubuntu

1. Clone this repo
2. Create the virtual environment
3. Activate the virtual environment
4. Upgrade your pip
5. Install the required libraries for FreeLabel
6. Recompile freelabel for your machine
7. Run the Django project (gets the server running at background)

```bash
git clone https://github.com/petteriTeikari/FreeLabel_WACV
conda create -n freelabel_venv python=3.6
conda activate freelabel_venv
python -m pip install --upgrade pip
pip install -r requirements.txt
cd freelabel && python setup.py build_ext --inplace && cd ..
python manage.py runserver 0.0.0.0:9000
```

8. Now that you have the server running, you can go to your browser: http://localhost:9000/freelabel/
9. Create username/password (you just get an own folder under `static`), does not matter if you get security alert, like:

![alt text](https://raw.githubusercontent.com/petteriTeikari/FreeLabel_WACV/master/figures/ignoreThisWarning.png)



10. Login with these details
11. Hit **"Play!"** (with defaults you might for example get this)

![alt text](https://raw.githubusercontent.com/petteriTeikari/FreeLabel_WACV/master/figures/pascalVOC_default.png)

##### How to customize

Check [Notes_on_FreeLabel.pdf](https://github.com/petteriTeikari/FreeLabel_WACV/blob/master/Notes_on_FreeLabel.pdf) for how the software is designed. 

1) You probably want to use your custom images instead of the PASCAL VOC images, images are defined on `imgList2.txt` imported from [`views.py`](https://github.com/petteriTeikari/FreeLabel_WACV/blob/69fcba110269886a31d660bc9409bb3a7bf388ee/freelabel/views.py#L46), which in default refer to some Google Drive files. `Note!` hard-coded separators `/` for paths, so forget about using Windows without customizing the code :P

![alt text](https://raw.githubusercontent.com/petteriTeikari/FreeLabel_WACV/master/figures//googleDriveID.png)

2) TODO! a simple image list switch does not do the trick for our custom images :( with at least `main.js:211 Uncaught TypeError: Cannot read property 'length' of undefinedat createAgainList (main.js:211)` occurring first

![alt text](https://raw.githubusercontent.com/petteriTeikari/FreeLabel_WACV/master/figures/createAgainList_bug.png)

##### Troubleshooting

If you get with "7) Django", the following `ValueError: numpy.ufunc has the wrong size, try recompiling. Expected 192, got 216`, came from re-compiling FreeLab before step "6)" causing the mismatch with NumPy versions. Delete the `build` and re-build. 
