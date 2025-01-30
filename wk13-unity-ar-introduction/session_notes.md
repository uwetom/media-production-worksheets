# Ar Introduction

## First (Tom 10 mins)

- Check correct version
	+ unity 2023.2.20f1
	+ installed infolder without spaces
	+ Android build
	
- Create new universal 3D project

## Intro to project and AR and ideation (Rod 1h)


## Set up template (Tom 1 h)

- AR foundation
	- [foundation documentation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@5.1/manual/index.html)
- Project Setup
	+ install Package manager > Unity Registry > "ar foundation"
	+ RESTART
	+ install Package manager > Unity Registry > "Google ARCore XR Plugin"
	+ switch to Android build
	+ Project settings > XR Plug-in Management > Android > ARcore
	+ Project Validation > Android
	+ In player settings 
		* delete vulcan graphics api
	+ Render features
		* Assets > settings > UPR - balanced
			- add render feature
				+ AR backbackground render feature

### Create scene

- New urp scene
- add xr > xr origin
- add XR > AR session
- add cube
- save scene
- run

- try to play


### Setup device

screen copy

https://github.com/Genymobile/scrcpy/blob/master/doc/macos.md


- turn on developer mode on tablet
- turn on usb debugging
- plug in to computer
- accept debugging


### build to device

- build settings
- **IMPORTANT** change scene
- change run device
- build
- mine took 5 mins first time, 
<!--stackedit_data:
eyJoaXN0b3J5IjpbODI0MDEzMzM4XX0=
-->