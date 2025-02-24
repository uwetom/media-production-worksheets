## VR 2 notes

### Intro

- Vr interactions 
- At the end of the session make sure you have built your project to a headset

### new project and scene

- Make new Vr core project

- xr interaction toolkit

- Open basic scene
- save as



### simple Interactable

Need an interactor and interactable

- show ray interactor on right controller

- add cube
- add simple interactable component
- show events


### script

- Create new script

public void Hovered(){
	Debug.Log("hovered");
}

public void Selected(){
	Debug.Log("Selected");

}

public void Activated(){
	Debug.Log("activated");
}

- Put it on the cube

- hook up the events

- add colour changer

GetComponent<Renderer>().material.SetColor("_BaseColor",Color.red);


- build to headset

- BREAK

### UI

- create canvas
- XR > UI CANVAS
- scale to 0.02
- world space
- add panel, textbox and button to canvas
- change button highlighted and pressed colour


creat new script


    public void Selected(){
        Instantiate(prefabObject, new Vector3(0,5,2), Quaternion.identity);
    }
 
add to button

hook up script

