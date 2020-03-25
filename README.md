# FreeLabel: A Publicly Available Annotation Tool based on Freehand Traces

Dias, Philipe Ambrozio, Zhou Shen, Amy Tabb, and Henry Medeiros. **"Freelabel: A publicly available annotation tool based on freehand traces."** In *2019 IEEE Winter Conference on Applications of Computer Vision (WACV)*, pp. 21-30. IEEE, 2019. https://doi.org/10.1109/WACV.2019.00010

This repository forked from [BitBucket](https://bitbucket.org/phil_dias/freelabel-wacv/src/master/) / https://github.com/philadias/freelabel/tree/beta_custom_datasets

Available under the Non-Profit Open Software License: for more details https://opensource.org/licenses/NPOSL-3.0

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
11. Hit **"Custom Dataset"** (with defaults you might for example get this)

##### How to customize

Check [Notes_on_FreeLabel.pdf](https://github.com/petteriTeikari/FreeLabel_WACV/blob/master/Notes_on_FreeLabel.pdf) for how the software is designed. 

1) You probably want to use your custom images instead of the PASCAL VOC images, images are loaded from the prompted directory with the default value, defined there [customsetB.js](https://github.com/petteriTeikari/FreeLabel_WACV/blob/bc22b8a86a78e2799cfc5007e76e2ef5607aeca0/static/js/customsetB.js#L18)

2) Getting the `replace()` error now?

![alt text](https://raw.githubusercontent.com/petteriTeikari/FreeLabel_WACV/master/figures/replace_error.png)
