define e = Character("Lucy", color="#FF5175")
define e_frightened = Character("Lucy", color="#FF5175")
define bgm = "tropical-alarm-clock-168821.mp3"
define fire_alarm = "fire-alarm-33770"
image e = "object-removebg-preview.png"
image e_frightened = "very_panicked-removebg-preview.png"
label start:
    play music bgm loop
    scene waking up morning
    with fade
    pause 6 
    scene background morning
    with fade
    show e at right
    with fade
    e "Good morning! How should we solve breakfast?"
    menu:
        "Cook at home.":
            jump fire
        "We could go to the restaurant...":
            jump restaurant
label fire:
    scene fire
    with slideright
    play sound fire_alarm
    show e_frightened at left
    with slideright
    e_frightened "Oh my! Call 911 quickly! My cooking skills are so bad that we can only go to the restaurant..."
    jump restaurant
label restaurant:
    scene restaurant
    with dissolve
    pause 3
    show e
    with fade
    e "What do you want to do next?"
    menu:
        "Go watch a movie!":
            jump movie
        "Let go back home at read a book together!":
            jump read
label movie:
    scene movie
    with fade
    pause 6
    show e at right
    e "We should go back home now! I'll read you a bedtime story."
    jump read
label read:
    scene read
    with fade
    pause 6
    show e at right
    e "It's late now, let's sleep baby..."
    jump night
label night:
    scene night
    pause 6
    return
