# gal.jpg image drawer

i found the picture [original.jpg](https://raw.githubusercontent.com/yungztr/gal.jpg/main/original.jpeg) on my pictures folder and wanted the code on the left.
sadly, i couldnt find a trace to the original picture, so I decided to copy it on my own
you will need to download [Processing](https://processing.org/) to run it. its similiar to arduino IDE

i couldnt copy the code on the pic 1:1 because its kinda cut off, but it still works regardless
might need to adjust some parameters etc.

it still feels kinda off tho

somebody help me find the original code too or the creater of the above image!!!

i will copy the code I have in this readme too, so that google will index this file somehow and that more people will find it hopefully if they ever search for this!!!

```
PImage pic;

void setup(){
    size(1000, 1000);
    pic = loadImage("gal.jpeg");
}

void draw() {
    background(0);

    int mountX = 300;
    int mountY = 300;

    pic.resize(mountX, mountY);

    float w = (float) width / mountX;
    float h = (float) width / mountY;

    for(int i = 0; i < mountX; i++) {
        for(int j = 0; j < mountY; j++) {
            color c = pic.get(i, j);
            float bri = brightness(c);

            push();
            translate(i * w, j * h);
            if (bri > 80) {
                float conf = map(bri,
                0, 255,
                0, 1);
                fill(255);
                ellipseMode(CORNER);
                ellipse(0, 0, w * conf, h);
            }
            pop();
        }
    }
}
```
