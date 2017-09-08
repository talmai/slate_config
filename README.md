# slate_config
Slate config file

## Content:

>> cat .slate

# Default to the current screen if the screen the reference does not exist.
config defaultToCurrentScreen true
# The base value for nudge percent calculation
config nudgePercentOf screenSize
# The base value for resize percent calculation
config resizePercentOf screenSize
#show icons on window hints
config windowHintsShowIcons true
#show icons for windows that are below focus
config windowHintsIgnoreHiddenWindows false
#spread out the window hint options
config windowHintsSpread true


# Monitor Aliases
alias mon-laptop      1680x1050
alias mon-hp          1080x3840

# Positional Aliases
alias full move screenOriginX;screenOriginY screenSizeX;screenSizeY
alias lefthalf move screenOriginX;screenOriginY screenSizeX/2;screenSizeY
alias leftthird move screenOriginX;screenOriginY screenSizeX/3;screenSizeY
alias righthalf move screenOriginX+screenSizeX/2;screenOriginY screenSizeX/2;screenSizeY
alias rightthird move screenOriginX+screenSizeX/3+screenSizeX/3;screenOriginY screenSizeX/3; screenSizeY
alias middlethird move screenOriginX+screenSizeX/3;screenOriginY screenSizeX/3;screenSizeY
alias tophalf move screenOriginX;screenOriginY screenSizeX;screenSizeY/2
alias bottomhalf move screenOriginX;screenOriginY+screenSizeY/2 screenSizeX;screenSizeY/2
alias topleft corner top-left resize:screenSizeX/2;screenSizeY/2
alias topright corner top-right resize:screenSizeX/2;screenSizeY/2
alias bottomleft corner bottom-left resize:screenSizeX/2;screenSizeY/2
alias bottomright corner bottom-right resize:screenSizeX/2;screenSizeY/2

# Default Layouts
default 2monitors resolutions:${mon-laptop};${mon-hp}
default 1monitor  resolutions:${mon-laptop}

#Layouts
#layout 2monitors 'Microsoft Outlook' ${tophalf} ${mon-hp}
#layout 2monitos 'iTerm' ${bottomhalf} ${mon-hp}

#alias
bind left:cmd;ctrl ${lefthalf}
bind right:cmd;ctrl ${righthalf}
bind up:cmd;ctrl ${tophalf}
bind up:cmd;ctrl;shift ${full}
bind down:cmd;ctrl ${bottomhalf}
#bind s:${hyper} focus 'Sublime Text 2'
bind e:cmd;ctrl hint
