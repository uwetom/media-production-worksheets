# 3D scanning

For this worksheet we will be using phones and tablets to 3D scan objects and people into a 3D meshes. Will then clean up these meshes to use in our projects.

# 1. Reality Scan

To scan objects we will use [Reality scan](https://www.realityscan.com/en-US) from Epic games who make the Unreal Game Engine.

Reality scan uses photogrammetry to create a 3D model from pictures of an object. 

## Download the app

You can find the app on the android of Apple store

[https://www.realityscan.com/en-US/mobile](https://www.realityscan.com/en-US/mobile)

You can or even use a web based version where you can upload images.

## Principles of Photogrammetry 

Before we scan anything we need consider how photogrammetry works so that we can get the best quality scan.

### Image Quality

Each image needs to be sharp, not blurry or noisy
	- Move the camera slowly
	- Ensure there is plenty of light.
	
### Subject Coverage

The entire object needs to be captured, take photos above and bellow the object and circle it to at multiple heights to capture all the details.

### Information Overlap

Each image should overlap with another so that common reference points on each photo can be used to stitch together the whole object.

## Environment

We also need to make sure the environment is consistent through out the scan to ensure the images all match

- If you are outside, choose a grey day to avoid harsh shadows or the light levels changing during the scan
- no wind, the object or background should not move during the scan.

# 2. Scan an object

Some objects are more suitable then other and will give better results

Avoid objects which are:
- Transparent
- Shiny
- Plain

Organic objects with texture and detail work best.

- Find a suitable small object to scan
- Place it somewhere you can access every side to get the best angle or use a turn table
- Open the app and press the plus symbol to create a new scan.

- [reality scan youtube site](https://www.youtube.com/@RealityScanOfficial)

# 3. Export the scan

Once you have finished scanning your object you need to wait for it to process it locally.

At this stage you want to look at the point cloud and see how it looks. If lots of bits are missing or missaligned you may want to consider rescanning the object differently to improve the results.


## Get your scan

You can either download or send it to sketchfab.

If you Export the model to sketchfab you can download it as an .obj file which will import to most 3D packages.

If you export straight from the app you will get a .zip file containing a .glb file, these can be difficult to open in some packages, but there are lots of tools ways to convert the file to a different format.

[https://convert3d.org/glb-to-fbx](https://convert3d.org/glb-to-fbx)

# 4. Import your scan

We can now import our scans in to Maya to clean them up if needed.

- Make a new Maya file 
- Import your model


# Additional resources

## Other photogrametry apps

There are other photogrametry apps available which you can experiment with for you own project, I particularly recomend:
- [polycam](https://poly.cam/tools/photogrammetry)
- [Kiriengine](https://www.kiriengine.app/)

If you are on a PC, you can also use the reality scan PC add through the Epic games launcher which has many more options for refining you scan.

-[reality scan](https://www.realityscan.com/en-US)

## More tutorials

- [How to use reality scan for mobile](https://www.youtube.com/watch?v=spPIqK3NVwc)
- [reality scan youtube site](https://www.youtube.com/@RealityScanOfficial)

# References

[three principles](https://dev.epicgames.com/community/learning/courses/blA/unreal-engine-realityscan-photogrammetry-basics-by-quixel/RklR/unreal-engine-realityscan-scanning-basics) 
