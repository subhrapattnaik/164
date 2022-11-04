# 164

https://drive.google.com/file/d/1l5z3sM1VSDbY-nVgsPU-SX0tXt1fgq3h/view?pli=1

A-Frame NAVIGATION MESHES
-----------------------------


1.create navigation meshes.
2.Learn about the A-Frame movement component.

-----------------------

We were able to cross through objects in the scene. Also every time we were loading the game, the objects were at random positions.



 In A-Frame virtual environment scenes we have bounding shapes that decide the collision area for the 3D objects in the scene.
 for every object in the game scene we can write the collision detection algorithm whether the object is colliding with the shooter's 
 gun weapon such that we don't cross through those objects.Well, that is going to be a very long way to make objects as obstacles and 
 not let the weapon pass through them.
 ******************************************************************
 an A-Fame virtual environment we can create user navigation meshes to create walkable and non-walkable areas for the user.
In today's class we will be learning how to create a navigation mesh model that will help us to walk around the scene without passing through the objects.
******************************************************************
Activity1
[
Here I have a very basic scene with few boxes lying around forming a very basic maze like structure.
Let’s see the arrangement of boxes in the A-Frame Visual Inspector tool.
We can use <Ctrl+Alt+i> keys together to open the Visual Inspector tool.
-------------------------------------
Now suppose we have to find a way to the red box, for this we need to move only in the plane area where there is no box.
But now if we move around the scene we can directly move to the red box. We do not have to worry about the boxes lying around our way to the red box.
In real life when you walk, you do not keep on crossing everything, right?


Everything that comes your way acts as obstacles.
To be able to reach the red box without passing through the blue boxes we should divide the scene
into walkable and non-walkable (obstacles) areas.
To do this, we will use A-Frame navigation meshes.



Navigation is basically determining the position to follow a particular route.

3D structures are also called meshes.


Now, we will be learning to create navigation mesh or in short the navmesh of our scene.
******************************************************
A navigation mesh is a polygon mesh that defines which areas of an environment are traversable.

To create navmesh in A-Frame we will use the “aframe-inspector-plugin-recast” library.
Link:
https://recast-api.donmccurdy.com/a frame-inspector-plugin-recast.js
<The teacher adds the library link in the <head> tag.>
  
And we will use the “inspector-plugin-recast” component of the library.
This will add the navmesh builder plugin window at the bottom of the A-Frame Visual Inspector tool.
  
  
  he teacher attaches the component to the scene element.>
<The teacher opens the Visual Inspector and shows the navmesh builder plugin added.>
  
  
  
  Now once the navmesh builder is added, all we have to do is click on the “Build” button to create the navmesh.
  ******************************************************
  
  Once you click on Build, the navmesh is created.
The blue area is the one which is walkable.
The non-walkable area is converted into holes where the objects of the scenes are placed.
  **********************************************
  
  We do not need to modify the default properties in the navmesh builder but we can just change one property, cellSize, to increase the precision of the holes cut around the boxes.
Also did you notice there is an extra hole in front of all the shapes even though there is nothing on the plane there?
****************************************************
  this is because every entity which is a part of the scene is considered as an object, and the camera is placed which has also become a part of the navmesh.
We should not include cameras in the navmesh, otherwise we won’t be able to walk in the scene.
  ----------------------------
  
  While building meshes we have to keep in mind that we do not include the camera in the scene.
  
  comment the camera entity in the code for now and open Visual Inspector again.
We can also set the cellSize property to 0.2 and build the navmesh.
  
  Once the navmesh is created now we can “Export” it.
This will create a gLTF model file of navmesh.
  
  -------------------------------------
  
  Once the file is downloaded, go to the download folder and copy the file into your working folder.
  
  To see how navmesh looks after it has been converted to the gLTF file, we can use the gLTF viewer.
Link:
https://gltf-viewer.donmccurdy.com/
  
  --------------------------------------
  
  add the gltf in assets
  
  create an entity for navigation mesh and link it with asset
  
  ------------------------------------
  
  Still the navigation mesh does not work!
To move around the scene containing the navmesh, we need to use the “movement-controls” component which is a part of “aframe-extras” library.
Link:
https://cdn.jsdelivr.net/gh/donmccur dy/aframe-extras@v6.1.1/dist/afram e-extras.min.js
  
  
  Let’s add the movement-controls component we using <a-entity>:
  
  We can set the speed and constrainToNavMesh properties of the movement-controls component.
  
  The camera and cursor entity must be the child entity of the movement-controls entity.
● Also the position of the movement-controls entity must be ahead of the camera in the positive z-axis.
  
  -----------------------------------------
  
  You can see that now the camera entity will not cross through the objects in the scene.
  
  Since you have learned how to create navigation meshes, you will create the navigation of our game environment.
  
  ---------------------------------------

https://www.youtube.com/watch?v=bkXLzu8VmDA
