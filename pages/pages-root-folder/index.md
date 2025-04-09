---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header_laboratory.png
permalink: /index.html

widget1:
  title: "Downloads"
  url: '/datasets/index.html'
  image: downloads.png
  text: ''
widget2:
  title: "Acquisition System"
  url: '/system/index.html'
  image: acquisition_system.png
  text: ''
widget3:
  title: "Usage"
  url: '/usage/index.html'
  image: usage_page.png
  text: ''

# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#

#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---


# Welcome to K2MUSE Dataset!
### — <font color="red">K2MUSE</font>: A Large-scale Human Lower limb Dataset of <font color="red">K</font>inematics, <font color="red">K</font>inetics, amplitude <font color="red">M</font>ode <font color="red">U</font>ltrasound and <font color="red">S</font>urface <font color="red">E</font>lectromyography

### — We hope that this dataset serves as the 'Key To MUSE' in your research.


Do you like the project? Please star🌟 us on GitHub to support the project! Thank you very much for your support!
<a href="https://github.com/k2muse/k2muse.github.io" title="Star me!" style="display:inline-block">
  <img src="https://img.shields.io/github/stars/k2muse/k2muse.github.io.svg?style=social" alt="Star me!" style="width: 75px; height: 20px;">
</a>


## Introduction
##### we present the *[K2MUSE dataset]*, which includes kinematic, kinetic, amplitude-mode ultrasound (AUS), and surface electromyography (sEMG) data. The proposed dataset includes lower-limb multimodal data from 30 able-bodied participants walking under different inclines (0°, ±5°, ±10°), various speeds (0.5 m/s, 1.0 m/s, and 1.5 m/s), and different non-ideal acquisition conditions. The kinematic and ground reaction force data were collected using a Vicon motion capture system and an instrumented treadmill with embedded force plates, while sEMG and AUS data were synchronously recorded for thirteen muscles on bilateral lower limbs. This dataset offers a new resource for designing control frameworks for rehabilitation robots and conducting biomechanical analysis of lower-limb locomotion.
