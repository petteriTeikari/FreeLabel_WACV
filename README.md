# FreeLabel: A Publicly Available Annotation Tool based on Freehand Traces

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

22

10. Login with these details
11. Hit **"Play!"**

##### How to customize

Check [Notes_on_FreeLabel.pdf](https://github.com/petteriTeikari/FreeLabel_WACV/blob/master/Notes_on_FreeLabel.pdf) for how the software is designed. 

1) You probably want to use your custom images instead of the PASCAL VOC images, images are defined on `imgList2.txt` imported from [`views.py`](https://github.com/petteriTeikari/FreeLabel_WACV/blob/69fcba110269886a31d660bc9409bb3a7bf388ee/freelabel/views.py#L46), which in default refer to some Google Drive files. `Note!` hard-coded separators `/` for paths, so forget about using Windows without customizing the code :P

##### Troubleshooting

If you get with "7) Django", the following `ValueError: numpy.ufunc has the wrong size, try recompiling. Expected 192, got 216`, came from re-compiling FreeLab before step "6)" causing the mismatch with NumPy versions. Delete the `build` and re-build. 

## Original README.MD

Open-access manuscript: https://www.coviss.org/wp-content/uploads/2018/11/freelabel_preprint.pdf 

WACV proceedings: to be included

### Disclaimer: this project is the first experience of the involved students with Javascript and Django. Despite our efforts to keep it fairly organized and functional, there is significant room for improvement. We appreciate any feedback for improving the tool, but cannot provide any type of support/warranty

### Available under the Non-Profit Open Software License: for more details https://opensource.org/licenses/NPOSL-3.0

## Notes on code organization: check Notes_on_FreeLabel.pdf

## Requirements:
- python3 and corresponding pip3
- virtualenv, which can be installed through 'pip install virtualenv' (see https://virtualenv.pypa.io/en/latest/installation/)

## Download, configuration and deploying the interface:
1. clone repository
2. cd freelabel-wacv/
3. create virtual environment: virtualenv . (if you have multiple python versions, run: virtualenv -p python3 .)
4. enter virtual environment: source ./bin/activate
5. install requirements: pip install -r requirements.txt (if it fails, try upgrading pip: pip install --upgrade pip)
6. Recompile callRGR: 
	- cd freelabel
	- python setup.py build_ext --inplace
	- cd ..
	
7. run Django project: python manage.py runserver 0.0.0.0:9000

---

## Accessing the interface:
1. access http://localhost:9000/freelabel/
2. register user/password (no need for email)
2. login with registered user
3. Done!
