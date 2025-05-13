# assignment6
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;
    public float jumpSpeed = 8f;
    private float direction = 0f;
    private Rigidbody2D player;

    // Start is called before the first frame update
    void Start()
    {
        player = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        direction = Input.GetAxis("Horizontal");

        if (direction > 0f)
        {
            player.linearVelocity = new Vector2(direction * speed, player.linearVelocity.y);
        }
        else if (direction < 0f)
        {
            player.linearVelocity = new Vector2(direction * speed, player.linearVelocity.y);
        }
        else
        {
            player.linearVelocity = new Vector2(0, player.linearVelocity.y);
        }

        if (Input.GetButtonDown("Jump"))
        {
            player.linearVelocity = new Vector2(player.linearVelocity.x, jumpSpeed);
        }
    }
}
using UnityEngine;
using UnityEngine.SceneManagement;
public class death : MonoBehaviour
{
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    private void OnCollisionEnter2D (Collision2D collision)
    {   
        if (collision.gameObject.CompareTag("Player"))
        {
            SceneManager.LoadScene(0);
        }   
    }

}

reflection:
i changed the speed of my character in a different screenshot for my first edit and i made a death script and my character can respawn for my second edit.
i struggled with making the death script but neal helped me and eventually i figured it out. I also had trouble with the box colliders because they were too big and my player kept getting stuck i fixed it by making them smaller and making the platforms smaller.
I am most proud of the death script because it has no lag and it is very efficent and it works. 
