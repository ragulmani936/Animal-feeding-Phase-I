# Animal-feeding-Phase-I

## Aim: 
To develop a animal feeding game-Phase-1 using unity.

## Algorithm:

### Player Controller
### Step 1: Extract the package and in unity , asserts -> Import packages -> Custom packages and select the package. When we go to Assets folders we can see the course library which we extracted
### Step 2: If you want, drag a different material from Course Library > Materials onto the Ground object
### Step 3: Drag 1 Human, 3 Animals, and 1 Food object into the Hierarchy
### Step 4: Rename the character “Player”, then reposition the animals and food so you can see them
### Step 5: Adjust the XYZ scale of the food (2,2,2) so you can easily see it from above
### Step 6: In your Assets folder, create a “Scripts” folder, and a “PlayerController” script inside.Attach the script to the Player by dragging the c# file to the player and open in the inspector and check whether it is attached

### Flood Flight
### Step 1: Create a new “MoveForward” script, attach script to the Food Pizza by dragging the c# file to the pizza and open in the inspector and check whether it is attached
### Step 2: Create a new “Prefabs” folder, drag your food (Pizza) into Prefab folder, and a pop up raises-> choose Original Prefab
### Step 3: Select the Player in the hierarchy, then drag the pizza from your Prefabs folder onto the new Projectile Prefab box in the inspector
### Step 4: Rotate all animals on the Y axis by 180 degrees to face down
### Step 5: Select all three animals in the hierarchy and Add Component > Drag the Move Forward script from the Scripts into inspector
### Step 6: Edit their speed values and test to see how it looks. Drag all three animals into the Prefabs folder, choosing “Original Prefab”

## Program:
### Player Control: 
~~~
using System.Collections;
using System.Collections.Generic;
using System.Collections.Specialized;
using System.Diagnostics.Contracts;
using System.Security.Cryptography;
using System.Threading;
using UnityEngine;

public class playercontroller : MonoBehaviour
{
    public float horizontalInput;
    public float speed = 10.0f;
    public float xRange = 15f;
    public GameObject projectilePrefab;//for reuseing the object

    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        if (transform.position.x < -xRange)
        {
            transform.position = new Vector3(-xRange, transform.position.y, transform.position.z);
        }
        if (transform.position.x > xRange)
        {
            transform.position = new Vector3(xRange, transform.position.y, transform.position.z);

        }
        horizontalInput = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right * horizontalInput * Time.deltaTime * speed);

        if (Input.GetKeyDown(KeyCode.Space))
        {
            Instantiate(projectilePrefab, transform.position, projectilePrefab.transform.rotation);
        }

    }
}
~~~
### Move Forward:
~~~
using System.Collections;
using System.Collections.Generic;
using System.Threading;
using UnityEngine;

public class moveforward : MonoBehaviour
{
    public float speed = 40.0f;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(Vector3.forward * Time.deltaTime * speed);
    }
}
~~~

## Output:

![img1](https://github.com/ragulmani936/Animal-feeding-Phase-I/blob/main/img1.png)

## Result:
Animal feeding game-Phase-1 using unity is developed successfully.

