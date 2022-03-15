# Dmitry Poltaradnev

# Contacts

- Tel: **+375447309928**
- E-mail: **poltaradnev@gmail.com**
- Telegram: **dmitry_poltaradnev**
- Discord: **Dmitry (@Dmitry-Poltaradnev) (rs-school server)**

# About me

Personal information: I'm 32, I have a great desire to learn and develop in the frontend direction.

# My skills

## Main skills

- C#
- Unity3D
- HTML
- CSS
- Git

# Sample code

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SwipeController : MonoBehaviour
{
    public static bool tap, swipeLeft, swipeRight, swipeUp, swipeDown;
    private bool isDraging = false;
    private Vector2 startTouch, swipeDelta;

    private void Update()
    {
        tap = swipeDown = swipeUp = swipeLeft = swipeRight = false;
        #region ПК-версия
        if (Input.GetMouseButtonDown(0))
        {
            tap = true;
            isDraging = true;
            startTouch = Input.mousePosition;
        }
        else if (Input.GetMouseButtonUp(0))
        {
            isDraging = false;
            Reset();
        }
        #endregion

        #region Мобильная версия
        if (Input.touches.Length > 0)
        {
            if (Input.touches[0].phase == TouchPhase.Began)
            {
                tap = true;
                isDraging = true;
                startTouch = Input.touches[0].position;
            }
            else if (Input.touches[0].phase == TouchPhase.Ended || Input.touches[0].phase == TouchPhase.Canceled)
            {
                isDraging = false;
                Reset();
            }
        }
        #endregion

        //Просчитать дистанцию
        swipeDelta = Vector2.zero;
        if (isDraging)
        {
            if (Input.touches.Length < 0)
                swipeDelta = Input.touches[0].position - startTouch;
            else if (Input.GetMouseButton(0))
                swipeDelta = (Vector2)Input.mousePosition - startTouch;
        }

        //Проверка на пройденность расстояния
        if (swipeDelta.magnitude > 100)
        {
            //Определение направления
            float x = swipeDelta.x;
            float y = swipeDelta.y;
            if (Mathf.Abs(x) > Mathf.Abs(y))
            {

                if (x < 0)
                    swipeLeft = true;
                else
                    swipeRight = true;
            }
            else
            {

                if (y < 0)
                    swipeDown = true;
                else
                    swipeUp = true;
            }

            Reset();
        }
    }
    private void Reset()
    {
        startTouch = swipeDelta = Vector2.zero;
        isDraging = false;
    }
}
```

# Work experience

- Graduated from C # courses in 2018.
- I have experience in commercial development at GameDev company as a Junior 2D artist for one year.

# English level

B1
