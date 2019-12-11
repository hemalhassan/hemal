# hemal
#include<cstdio>
#include <windows.h>  // for MS Windows
#include <GL/gl.h>
#include <GL/glut.h>  // GLUT, include glu.h and gl.h
#include<math.h>>
#include<iostream>
using namespace std;
# define PI           3.14159265358979323846

//GLint mode;

int i;

GLfloat cloud_position1 = 0.0f;
GLfloat ship_position1 = 0.0f;
GLfloat ship_position2 = 0.0f;
GLfloat car_position1 = 0.0f;
GLfloat car_position2 = 0.0f;
GLfloat bus_position2 = 0.0f;
GLfloat metro_position1 = 0.0f;



GLfloat cloud_speed = 0.01f;
GLfloat ship_speed1 = 0.05f;
GLfloat ship_speed2 = 0.03f;
GLfloat car_speed1 = 0.04f;
GLfloat car_speed2 = 0.04f;
GLfloat bus_speed2 = 0.04f;
GLfloat metro_speed1 = 0.02f;

GLfloat Rain_positionX=0.0f;
GLfloat Rain_positionY=0.0f;
GLfloat Rain_speedX=.002f;
GLfloat Rain_speedY=.01f;
GLint rain_count=1000;

GLfloat plane_position=0.0f;
GLfloat plane_speed = 0.05f;


void Plane_update(int value) {

    if(plane_position >2.0)
        plane_position = -1.0f;

    plane_position += plane_speed;

	glutPostRedisplay();


	glutTimerFunc(100, Plane_update, 0);
}

void Rain_update (int value)
{
//    if(positionX<=-3 || positionY<=-3)
//    {
//        positionY=1;
//    }
    Rain_positionX-=Rain_speedX;
    Rain_positionY-=Rain_speedY;

    glutPostRedisplay();
	glutTimerFunc(20, Rain_update, 0);
}




void cloud_update1(int value) {

    if(cloud_position1 >1.8)
        cloud_position1 = -1.0f;

    cloud_position1 += cloud_speed;

	glutPostRedisplay();


	glutTimerFunc(100, cloud_update1, 0);
}




void ship_update1(int value) {

    if(ship_position1 <-1.0)
        ship_position1 = 1.0f;

    ship_position1 -= ship_speed1;

	glutPostRedisplay();


	glutTimerFunc(100, ship_update1, 0);
}




void ship_update2(int value) {

    if(ship_position2 >1.0)
        ship_position2 = -1.0f;

    ship_position2 += ship_speed2;

	glutPostRedisplay();


	glutTimerFunc(100, ship_update2, 0);
}




void car_update1(int value) {

    if(car_position1 >1.8)
        car_position1 = -1.0f;

    car_position1 += car_speed1;

	glutPostRedisplay();


	glutTimerFunc(100, car_update1, 0);
}


void car_update2(int value) {

    if(car_position2 >1.8)
        car_position2 = -1.0f;

    car_position2 += car_speed2;

	glutPostRedisplay();


	glutTimerFunc(100, car_update2, 0);
}

void bus_update2(int value) {

    if(bus_position2 <-1.4)
        bus_position2 = 1.0f;

    bus_position2 -= bus_speed2;

	glutPostRedisplay();


	glutTimerFunc(100, bus_update2, 0);
}


void metro_update1(int value) {

    if(metro_position1 >1.8)
        metro_position1 = -1.0f;

    metro_position1 += metro_speed1;

	glutPostRedisplay();


	glutTimerFunc(100, metro_update1, 0);
}

void init() {
   glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
}

void Idle()
{
    glutPostRedisplay();
}





void night(/*int value*/) {







	glClearColor(1.0f, 1.0f, 1.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);

	glLoadIdentity();
	glLineWidth(2.0);

	GLfloat x, y;
	int i;
	GLfloat radius;
	int triangleAmount = 20;
	GLfloat twicePi = 2.0f * PI;


	glBegin(GL_QUADS); //sky
	glColor3ub(19,24,98);
	glVertex2f(-1,1);
	glVertex2f(-1,.2);
    glVertex2f(1,.2);
    glVertex2f(1,1);
	glEnd();

	glPointSize(2);
	glBegin(GL_POINTS);
	glColor3f(1,1,1);
	glVertex2f(.9,.8); //virgo
	glVertex2f(.77,.73);
	glVertex2f(.73,.8);
	glVertex2f(.76,.84);
	glVertex2f(.62,.65);
	glVertex2f(.64,.8);
	glVertex2f(.57,.84);

	glVertex2f(.47,.98); //capricorn
	glVertex2f(.44,.75);
	glVertex2f(.46,.64);
	glVertex2f(.37,.77);
	glVertex2f(.32,.63);
	glVertex2f(.15,.7);
	glVertex2f(.2,.74);
	glVertex2f(.24,.77);
	glVertex2f(.2,.88);

	glVertex2f(.17,.96);//Leo
	glVertex2f(.1,.92);
	glVertex2f(.03,.83);
	glVertex2f(.08,.78);
	glVertex2f(.01,.81);
	glVertex2f(-.08,.65);
	glVertex2f(-.05,.6);
	glVertex2f(-.15,.53);
	glEnd();

	glTranslatef(-.7,0,0);
	glBegin(GL_POINTS);
	glVertex2f(.47,.98); //capricorn
	glVertex2f(.44,.75);
	glVertex2f(.46,.64);
	glVertex2f(.37,.77);
	glVertex2f(.32,.63);
	glVertex2f(.15,.7);
	glVertex2f(.2,.74);
	glVertex2f(.24,.77);
	glVertex2f(.2,.88);
	glEnd();
	glLoadIdentity();

	glTranslatef(-1.5,.1,0);
	glBegin(GL_POINTS);
	glColor3f(1,1,1);
	glVertex2f(.9,.8); //virgo
	glVertex2f(.77,.73);
	glVertex2f(.73,.8);
	glVertex2f(.76,.84);
	glVertex2f(.62,.65);
	glVertex2f(.64,.8);
	glVertex2f(.57,.84);
	glEnd();
	glLoadIdentity();

	glTranslatef(-1.0,-.4,0);
	glBegin(GL_POINTS);
	glColor3f(1,1,1);
	glVertex2f(.17,.96);//Leo
	glVertex2f(.1,.92);
	glVertex2f(.03,.83);
	glVertex2f(.08,.78);
	glVertex2f(.01,.81);
	glVertex2f(-.08,.65);
	glVertex2f(-.05,.6);
	glVertex2f(-.15,.53);
	glEnd();
	glLoadIdentity();

	//moon
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(202, 202, 202);
        x=.3f; y=.75f; radius =.1f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();
	//moon ends


	glPushMatrix();
    glTranslatef(cloud_position1,0.0f, 0.0f);

	//cloud 01 starts
	x=-.78f;
	y=.7f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.7f;
	y=.77f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.64f;
	y=.85f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.68f;
	y=.71f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.6f;
	y=.75f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.55f;
	y=.8f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	//2nd cloud starts
	glTranslatef(0.7f, 0.07f, 0.0f);
	x=-.78f;
	y=.7f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.7f;
	y=.77f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.64f;
	y=.85f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.68f;
	y=.71f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.6f;
	y=.75f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.55f;
	y=.8f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(8, 8, 8);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();
	glLoadIdentity();

	glLoadIdentity();

 glPopMatrix();

/////////////////////////////////////////////////////////////////////////////////////////////////////////

//Plane starts from here
	glPushMatrix();
    glTranslatef(plane_position,0.0f, 0.0f);
	glBegin(GL_QUADS);
	glColor3ub(94, 94, 91); //Aero-plane
	glVertex2f(-.8,.8);
	glVertex2f(-.8,.73);
	glVertex2f(-.65,.73);
	glVertex2f(-.65,.8);

	glVertex2f(-.8,.73);
	glVertex2f(-.8,.8);
	glVertex2f(-.85,.85);
	glVertex2f(-.85,.73);

	glColor3ub(237, 228, 104); //window
	glVertex2f(-.79,.78);
	glVertex2f(-.79,.75);
	glVertex2f(-.77,.75);
	glVertex2f(-.77,.78);

	glVertex2f(-.71,.78);
	glVertex2f(-.71,.75);
	glVertex2f(-.69,.75);
	glVertex2f(-.69,.78);

	glColor3ub(66, 66, 64); //wing
	glVertex2f(-.74,.8);
	glVertex2f(-.7,.8);
	glVertex2f(-.68,.85);
	glVertex2f(-.72,.8);

	glVertex2f(-.76,.765); //wing
	glVertex2f(-.77,.72);
	glVertex2f(-.77,.71);
	glVertex2f(-.72,.765);

	glVertex2f(-.85,.765); //wing
	glVertex2f(-.86,.72);
	glVertex2f(-.86,.71);
	glVertex2f(-.81,.765);
	glEnd();

	glBegin(GL_TRIANGLES);
	glColor3ub(66, 66, 64);//Aero-plane
	glVertex2f(-.65,.73);
	glVertex2f(-.6,.73);
	glVertex2f(-.65,.8);
	glEnd();

	glBegin(GL_LINES);
	glColor3f(0,0,0);
	glVertex2f(-.8,.8); //plane
	glVertex2f(-.85,.8);

	glVertex2f(-.65,.8);
	glVertex2f(-.65,.73);
	glEnd();
	glPopMatrix();
	glLoadIdentity();
    //planes ends here

////////////////////////////////////

    //metro
    glBegin(GL_QUADS);
	glColor3ub(15, 15, 15);

	glVertex2f(-1.0f, 0.36f);
	glVertex2f(1.0f, 0.36f);
	glVertex2f(1.0f, 0.38f);
	glVertex2f(-1.0f, 0.38f);

	glEnd();



    glPushMatrix();
    glTranslatef(metro_position1,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.0f, 0.4f);
	glVertex2f(0.2f, 0.4f);
	glVertex2f(0.2f, 0.5f);
	glVertex2f(0.0f, 0.5f);

	glEnd();

	 glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.23f, 0.4f);
	glVertex2f(0.43f, 0.4f);
	glVertex2f(0.43f, 0.5f);
	glVertex2f(0.23f, 0.5f);

	glEnd();


	glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.46f, 0.4f);
	glVertex2f(0.66f, 0.4f);
	glVertex2f(0.66f, 0.5f);
	glVertex2f(0.46f, 0.5f);

	glEnd();


    glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.2f, 0.42f);
	glVertex2f(0.23f, 0.42f);
	glVertex2f(0.23f, 0.44f);
	glVertex2f(0.2f, 0.44f);

	glEnd();


	 glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.2f, 0.46f);
	glVertex2f(0.23f, 0.46f);
	glVertex2f(0.23f, 0.48f);
	glVertex2f(0.2f, 0.48f);

	glEnd();


	  glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.43f, 0.42f);
	glVertex2f(0.46f, 0.42f);
	glVertex2f(0.46f, 0.44f);
	glVertex2f(0.43f, 0.44f);

	glEnd();


	glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.43f, 0.46f);
	glVertex2f(0.46f, 0.46);
	glVertex2f(0.46f, 0.48f);
	glVertex2f(0.43f, 0.48f);

	glEnd();



	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.02f, 0.42f);
	glVertex2f(0.08f, 0.42);
	glVertex2f(0.08f, 0.48);
	glVertex2f(0.02f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.12f, 0.42f);
	glVertex2f(0.18f, 0.42);
	glVertex2f(0.18f, 0.48);
	glVertex2f(0.12f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.02f, 0.42f);
	glVertex2f(0.08f, 0.42);
	glVertex2f(0.08f, 0.48);
	glVertex2f(0.02f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.25f, 0.42f);
	glVertex2f(0.31f, 0.42);
	glVertex2f(0.31f, 0.48);
	glVertex2f(0.25f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.35f, 0.42f);
	glVertex2f(0.41f, 0.42);
	glVertex2f(0.41f, 0.48);
	glVertex2f(0.35f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.48f, 0.42f);
	glVertex2f(0.54f, 0.42);
	glVertex2f(0.54f, 0.48);
	glVertex2f(0.48f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.58f, 0.42f);
	glVertex2f(0.64f, 0.42);
	glVertex2f(0.64f, 0.48);
	glVertex2f(0.58f, 0.48f);

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.05f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.15f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();



	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.28f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.38f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.51f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.61f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glPopMatrix();








//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


///building one

	glTranslatef(0.02f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.99f, 0.2f);
	glVertex2f(-0.96f, 0.2f);
	glVertex2f(-0.96f, 0.45f);
	glVertex2f(-0.99f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.96f, 0.2f);
	glVertex2f(-0.88f, 0.2f);
	glVertex2f(-0.88f, 0.45f);
	glVertex2f(-0.96f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.94f, 0.23f);
	glVertex2f(-0.90f, 0.23f);
	glVertex2f(-0.90f, 0.31f);
	glVertex2f(-0.94f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.94f, 0.33f);
	glVertex2f(-0.90f, 0.33f);
	glVertex2f(-0.90f, 0.41f);
	glVertex2f(-0.94f, 0.41f);

	glEnd();

	///

	///building two

	///side view
	glBegin(GL_QUADS);
	glColor3ub(7, 63, 107);

	glVertex2f(-0.86f, 0.2f);
	glVertex2f(-0.83f, 0.2f);
	glVertex2f(-0.83f, 0.35f);
	glVertex2f(-0.86f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(11, 84, 140);

	glVertex2f(-0.83f, 0.2f);
	glVertex2f(-0.75f, 0.2f);
	glVertex2f(-0.75f, 0.35f);
	glVertex2f(-0.83f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.81f, 0.23f);
	glVertex2f(-0.77f, 0.23f);
	glVertex2f(-0.77f, 0.31f);
	glVertex2f(-0.81f, 0.31f);

	glEnd();

	///

	///building three

	///side view
	glBegin(GL_QUADS);
	glColor3ub(11, 86, 20);

	glVertex2f(-0.73f, 0.2f);
	glVertex2f(-0.70f, 0.2f);
	glVertex2f(-0.70f, 0.65f);
	glVertex2f(-0.73f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(18, 124, 31);

	glVertex2f(-0.70f, 0.2f);
	glVertex2f(-0.62f, 0.2f);
	glVertex2f(-0.62f, 0.65f);
	glVertex2f(-0.70f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.23f);
	glVertex2f(-0.64f, 0.23f);
	glVertex2f(-0.64f, 0.31f);
	glVertex2f(-0.68f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.33f);
	glVertex2f(-0.64f, 0.33f);
	glVertex2f(-0.64f, 0.41f);
	glVertex2f(-0.68f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.43f);
	glVertex2f(-0.64f, 0.43f);
	glVertex2f(-0.64f, 0.51f);
	glVertex2f(-0.68f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.53f);
	glVertex2f(-0.64f, 0.53f);
	glVertex2f(-0.64f, 0.61f);
	glVertex2f(-0.68f, 0.61f);

	glEnd();

	///

	///building four

	///side view
	glBegin(GL_QUADS);
	glColor3ub(9, 91, 94);

	glVertex2f(-0.60f, 0.2f);
	glVertex2f(-0.57f, 0.2f);
	glVertex2f(-0.57f, 0.55f);
	glVertex2f(-0.60f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(12, 118, 122);

	glVertex2f(-0.57f, 0.2f);
	glVertex2f(-0.49f, 0.2f);
	glVertex2f(-0.49f, 0.55f);
	glVertex2f(-0.57f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.55f, 0.23f);
	glVertex2f(-0.51f, 0.23f);
	glVertex2f(-0.51f, 0.31f);
	glVertex2f(-0.55f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.55f, 0.33f);
	glVertex2f(-0.51f, 0.33f);
	glVertex2f(-0.51f, 0.41f);
	glVertex2f(-0.55f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.55f, 0.43f);
	glVertex2f(-0.51f, 0.43f);
	glVertex2f(-0.51f, 0.51f);
	glVertex2f(-0.55f, 0.51f);

	glEnd();

	///

	///building five

	///side view
	glBegin(GL_QUADS);
	glColor3ub(124, 9, 44);

	glVertex2f(-0.47f, 0.2f);
	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.44f, 0.35f);
	glVertex2f(-0.47f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(150, 13, 54);

	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.36f, 0.2f);
	glVertex2f(-0.36f, 0.35f);
	glVertex2f(-0.44f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.42f, 0.23f);
	glVertex2f(-0.38f, 0.23f);
	glVertex2f(-0.38f, 0.31f);
	glVertex2f(-0.42f, 0.31f);

	glEnd();

	///

	///building six

	///side view
	glBegin(GL_QUADS);
	glColor3ub(96, 87, 89);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(135, 124, 127);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
    glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	///building seven

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building eight

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building nine

	glTranslatef(+0.39f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(7, 63, 107);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(11, 84, 140);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	///building ten

	glTranslatef(-0.13f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building eleven

    glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(205, 216, 212);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(222, 232, 228);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building twelve

	glTranslatef(0.39f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(11, 86, 20);

	glVertex2f(-0.47f, 0.2f);
	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.44f, 0.35f);
	glVertex2f(-0.47f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(18, 124, 31);

	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.36f, 0.2f);
	glVertex2f(-0.36f, 0.35f);
	glVertex2f(-0.44f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.42f, 0.23f);
	glVertex2f(-0.38f, 0.23f);
	glVertex2f(-0.38f, 0.31f);
	glVertex2f(-0.42f, 0.31f);

	glEnd();

	///

	///building thirteen

	glTranslatef(-0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building fourteen

    glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building fifteen

	glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(9, 91, 94);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(12, 118, 122);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	glLoadIdentity();

//////////////////////////////////////////////////////////////////////////////////////////////////////////








glBegin(GL_QUADS); //upper water shade
	glColor3ub(123, 137, 147);
    glVertex2f(-1.0f, 0.18f);
    glVertex2f(1.0f, 0.18f);
    glVertex2f(1.0f, 0.2f);
    glVertex2f(-1.0f, 0.2f);
    glEnd();

    glBegin(GL_QUADS);              //water
	glColor3ub(0, 113, 167);

    glVertex2f(-1.0f, -0.5f);
    glVertex2f(1.0f, -0.5f);
	glVertex2f(1.0f, 0.18f);
    glVertex2f(-1.0f, 0.18f);
    glEnd();



//ship1
     glPushMatrix();
     glTranslatef(ship_position1,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.2f, 0.08f);
    glVertex2f(0.0f, 0.08f);
    glVertex2f(0.0f, 0.18f);
    glVertex2f(-0.2f, 0.18f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.3f, 0.18f);
    glVertex2f(-0.2f, 0.08f);
    glVertex2f(-0.2f, 0.18f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(29, 109, 155);

    glVertex2f(-0.12f, 0.18f);
    glVertex2f(-0.02f, 0.18f);
    glVertex2f(-0.02f, 0.26f);
    glVertex2f(-0.12f, 0.26f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(28, 109, 155);

    glVertex2f(-0.2f, 0.18f);
    glVertex2f(-0.12f, 0.18f);
    glVertex2f(-0.12f, 0.26f);

    glEnd();

    glBegin(GL_QUADS);          ///////window start
	glColor3ub(232, 228, 125);

    glVertex2f(-0.11f, 0.19f);
    glVertex2f(-0.08f, 0.19f);
    glVertex2f(-0.08f, 0.24f);
    glVertex2f(-0.11f, 0.24f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(-0.065f, 0.19f);
    glVertex2f(-0.035f, 0.19f);
    glVertex2f(-0.035f, 0.24f);
    glVertex2f(-0.065f, 0.24f);

    glEnd();
    glPopMatrix();

//ship1 ends




	//ship2

    glPushMatrix();
    glTranslatef(ship_position2,0.0f, 0.0f);

	glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.1f, -0.1f);
    glVertex2f(0.5f, -0.1f);
	glVertex2f(0.5f, 0.1f);
    glVertex2f(0.1f, 0.1f);

    glEnd();



    glBegin(GL_TRIANGLES);
    glColor3ub(169, 181, 183);

    glVertex2f(0.5f, -0.1f);
    glVertex2f(0.7f, 0.1f);
    glVertex2f(0.5f, 0.1f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.16f, 0.1f);
    glVertex2f(0.42f, 0.1f);
    glVertex2f(0.42f, 0.2f);
    glVertex2f(0.16f, 0.2f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.42f, 0.2f);
    glVertex2f(0.42f, 0.1f);
    glVertex2f(0.52f, 0.1f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.2f, 0.2f);
    glVertex2f(0.34f, 0.2f);
    glVertex2f(0.34f, 0.28f);
    glVertex2f(0.2f, 0.28f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.34f, 0.28f);
    glVertex2f(0.34f, 0.2f);
    glVertex2f(0.4f, 0.2f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.22f, 0.28f);
    glVertex2f(0.29f, 0.28f);
    glVertex2f(0.29f, 0.34f);
    glVertex2f(0.22f, 0.34f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.29f, 0.34f);
    glVertex2f(0.29f, 0.28f);
    glVertex2f(0.32f, 0.28f);

    glEnd();



    glBegin(GL_QUADS);     ///////window start low
	glColor3ub(232, 228, 125);

    glVertex2f(0.18f, 0.12f);
    glVertex2f(0.22f, 0.12f);
    glVertex2f(0.22f, 0.18f);
    glVertex2f(0.18f, 0.18f);

    glEnd();

      glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.24f, 0.12f);
    glVertex2f(0.28f, 0.12f);
    glVertex2f(0.28f, 0.18f);
    glVertex2f(0.24f, 0.18f);

    glEnd();


      glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.3f, 0.12f);
    glVertex2f(0.34f, 0.12f);
    glVertex2f(0.34f, 0.18f);
    glVertex2f(0.3f, 0.18f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.36f, 0.12f);
    glVertex2f(0.4f, 0.12f);
    glVertex2f(0.4f, 0.18f);
    glVertex2f(0.36f, 0.18f);

    glEnd();


     glBegin(GL_QUADS);        ///////window start 2nd low
	glColor3ub(232, 228, 125);

    glVertex2f(0.22f, 0.20f);
    glVertex2f(0.26f, 0.20f);
    glVertex2f(0.26f, 0.26f);
    glVertex2f(0.22f, 0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.28f, 0.20f);
    glVertex2f(0.32f, 0.20f);
    glVertex2f(0.32f, 0.26f);
    glVertex2f(0.28f, 0.26f);

    glEnd();

    glBegin(GL_QUADS);     ///////window start top
	glColor3ub(232, 228, 125);

    glVertex2f(0.24f, 0.28f);
    glVertex2f(0.28f, 0.28f);
    glVertex2f(0.28f, 0.33f);
    glVertex2f(0.24f, 0.33f);

    glEnd();


    glPopMatrix();
    //ship2 ends






    //dandy 1

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




//dandy golla1 ends

	//moon ends




    //dandy1

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();
    //dandy1 ends

    glLoadIdentity();
    glTranslatef(0.7f,0.0f,0.0f);



    ///dandy 2

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();

    //dandy 2 golla

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




    //dandy 2 golla1 ends

    ///


    glTranslatef(-1.4f,0.0f,0.0f);



    ///dandy 3

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();

    //dandy 2 golla

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




    //dandy golla1 ends

    ///

    glLoadIdentity();


/////////////////////////////////////////////////////////////////////////////////////////////////////







glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-1.0f,-.5f);
	glVertex2f(-1.0f,-.55f);
	glVertex2f(-.8f,-.55f);
	glVertex2f(-.8f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.8f,-.5f);
	glVertex2f(-.8f,-.55f);
	glVertex2f(-.6f,-.55f);
	glVertex2f(-.6f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.6f,-.5f);
	glVertex2f(-.6f,-.55f);
	glVertex2f(-.4f,-.55f);
	glVertex2f(-.4f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.4f,-.5f);
	glVertex2f(-.4f,-.55f);
	glVertex2f(-.2f,-.55f);
	glVertex2f(-.2f,-.5f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.2f,-.5f);
	glVertex2f(-.2f,-.55f);
	glVertex2f(.0f,-.55f);
	glVertex2f(.0f,-.5f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.0f,-.5f);
	glVertex2f(.0f,-.55f);
	glVertex2f(.2f,-.55f);
	glVertex2f(.2f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.2f,-.5f);
	glVertex2f(.2f,-.55f);
	glVertex2f(.4f,-.55f);
	glVertex2f(.4f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.4f,-.5f);
	glVertex2f(.4f,-.55f);
	glVertex2f(.6f,-.55f);
	glVertex2f(.6f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.6f,-.5f);
	glVertex2f(.6f,-.55f);
	glVertex2f(.8f,-.55f);
	glVertex2f(.8f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.8f,-.5f);
	glVertex2f(.8f,-.55f);
	glVertex2f(1.0f,-.55f);
	glVertex2f(1.0f,-.5f);
	glEnd();

	//////////////////////////////////////////////////////road piller 2///////////////////////////////////////////

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-1.0f,-.95f);
	glVertex2f(-1.0f,-1.0f);
	glVertex2f(-.8f,-1.0f);
	glVertex2f(-.8f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.8f,-.95f);
	glVertex2f(-.8f,-1.0f);
	glVertex2f(-.6f,-1.0f);
	glVertex2f(-.6f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.6f,-.95f);
	glVertex2f(-.6f,-1.0f);
	glVertex2f(-.4f,-1.0f);
	glVertex2f(-.4f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.4f,-.95f);
	glVertex2f(-.4f,-1.0f);
	glVertex2f(-.2f,-1.0f);
	glVertex2f(-.2f,-.95f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.2f,-.95f);
	glVertex2f(-.2f,-1.0f);
	glVertex2f(.0f,-1.0f);
	glVertex2f(.0f,-.95f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.0f,-.95f);
	glVertex2f(.0f,-1.0f);
	glVertex2f(.2f,-1.0f);
	glVertex2f(.2f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.2f,-.95f);
	glVertex2f(.2f,-1.0f);
	glVertex2f(.4f,-1.0f);
	glVertex2f(.4f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.4f,-.95f);
	glVertex2f(.4f,-1.0f);
	glVertex2f(.6f,-1.0f);
	glVertex2f(.6f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.6f,-.95f);
	glVertex2f(.6f,-1.0f);
	glVertex2f(.8f,-1.0f);
	glVertex2f(.8f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.8f,-.95f);
	glVertex2f(.8f,-1.0f);
	glVertex2f(1.0f,-1.0f);
	glVertex2f(1.0f,-.95f);
	glEnd();

///////////////////////////////////////////main road/////////////////////

    glBegin(GL_QUADS);
	glColor3ub(122, 132, 147);
	glVertex2f(-1.0f,-.55f);
	glVertex2f(-1.0f,-.95f);
	glVertex2f(1.0f,-.95f);
	glVertex2f(1.0f,-.55f);
	glEnd();

//////////////////////////////////////road division////////////////////////




	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.8f,-.73f);
	glVertex2f(-.8f,-.75f);
	glVertex2f(-.6f,-.75f);
	glVertex2f(-.6f,-.73f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.4f,-.73f);
	glVertex2f(-.4f,-.75f);
	glVertex2f(-.2f,-.75f);
	glVertex2f(-.2f,-.73f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.0f,-.73f);
	glVertex2f(.0f,-.75f);
	glVertex2f(.2f,-.75f);
	glVertex2f(.2f,-.73f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.4f,-.73f);
	glVertex2f(.4f,-.75f);
	glVertex2f(.6f,-.75f);
	glVertex2f(.6f,-.73f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.8f,-.73f);
	glVertex2f(.8f,-.75f);
	glVertex2f(1.0f,-.75f);
	glVertex2f(1.0f,-.73f);
	glEnd();

///////////////////////////////////////////////////////////////////////bus 1///////////////////////////////////////////




     glPushMatrix();
     glTranslatef(car_position1,0.0f, 0.0f);

    glBegin(GL_POLYGON);
	glColor3ub(201, 53, 12);
	glVertex2f(-.9f,-.45f);
	glVertex2f(-.9f,-.55f);
	glVertex2f(-.5f,-.55);
	glVertex2f(-.5f,-.53f);
	glVertex2f(-.55f,-.45f);
	glEnd();

	////////////////////window
    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.87f,-.47f);
	glVertex2f(-.87f,-.53f);
	glVertex2f(-.82f,-.53f);
	glVertex2f(-.82f,-.47f);
	glEnd();

     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.80f,-.47f);
	glVertex2f(-.80f,-.53f);
	glVertex2f(-.75f,-.53f);
	glVertex2f(-.75f,-.47f);
	glEnd();


     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.73f,-.47f);
	glVertex2f(-.73f,-.53f);
	glVertex2f(-.68f,-.53f);
	glVertex2f(-.68f,-.47f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.66f,-.47f);
	glVertex2f(-.66f,-.53f);
	glVertex2f(-.61f,-.53f);
	glVertex2f(-.61f,-.47f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.59f,-.47f);
	glVertex2f(-.59f,-.53f);
	glVertex2f(-.51f,-.53f);
	glVertex2f(-.55f,-.47f);
	glEnd();


////////////////////////////////////body////////////

    glBegin(GL_QUADS);
	glColor3ub(30, 32, 145);
	glVertex2f(-.9f,-.55f);
	glVertex2f(-.9f,-.65f);
	glVertex2f(-.5f,-.65);
	glVertex2f(-.5f,-.55f);
	glEnd();

//////////////////////////////wheel1////////////////
 GLfloat bus1x=-.8f; GLfloat bus1y=-.64f; GLfloat bus1radius =.04f;
	int bus1i;
	int bus1lineAmount = 100;
	GLfloat bus1twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus1i = 0; bus1i <= bus1lineAmount;bus1i++) {
			glVertex2f(
			    bus1x + (bus1radius * cos(bus1i *  bus1twicePi / bus1lineAmount)),
			    bus1y + (bus1radius* sin(bus1i * bus1twicePi / bus1lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat bus1x2=-.6f; GLfloat bus1y2=-.64f; GLfloat bus1radius2 =.04f;
	int bus1i2;
	int bus1lineAmount2 = 100;
	GLfloat bus1twicePi2 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus1i2 = 0; bus1i2 <= bus1lineAmount2;bus1i2++) {
			glVertex2f(
			    bus1x2 + (bus1radius2 * cos(bus1i2 *  bus1twicePi2 / bus1lineAmount2)),
			    bus1y2 + (bus1radius2* sin(bus1i2 * bus1twicePi2 / bus1lineAmount2))
			);
		}
	glEnd();

	glPopMatrix();


//////////////////////////////////car///////////////////////////////////////////




    glPushMatrix();
    glTranslatef(car_position2,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(193, 211, 25);
	glVertex2f(-.06f,-.47f);
	glVertex2f(-.11f,-.53f);
	glVertex2f(.10f,-.53);
	glVertex2f(.06f,-.47f);
	glEnd();

	///////////////////////////window/////////////////

    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.05f,-.48f);
	glVertex2f(-.09f,-.52f);
	glVertex2f(-.01f,-.52f);
	glVertex2f(-.01f,-.48f);
	glEnd();

     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.01f,-.48f);
	glVertex2f(.01f,-.52f);
	glVertex2f(.08f,-.52f);
	glVertex2f(.05f,-.48f);
	glEnd();

    ////////////////////////////body///////////////////

     glBegin(GL_POLYGON);
	glColor3ub(111, 119, 29);
	glVertex2f(-.11f,-.53f);
	glVertex2f(-.15f,-.55f);
	glVertex2f(-.15f,-.6f);
	glVertex2f(.16f,-.6f);
	glVertex2f(.16f,-.56f);
	glVertex2f(.10f,-.53f);
	glEnd();


	//////////////////////////////wheel1////////////////
 GLfloat car1x=-.07f; GLfloat car1y=-.6f; GLfloat car1radius =.025f;
	int car1i;
	int car1lineAmount = 100;
	GLfloat car1twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(car1i = 0; car1i <= car1lineAmount;car1i++) {
			glVertex2f(
			    car1x + (car1radius * cos(car1i *  car1twicePi / car1lineAmount)),
			    car1y + (car1radius* sin(car1i * car1twicePi / car1lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat car1x1=.07f; GLfloat car1y1=-.6f; GLfloat car1radius1 =.025f;
	int car1i1;
	int car1lineAmount1 = 100;
	GLfloat car1twicePi1 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(car1i1 = 0; car1i1 <= car1lineAmount1;car1i1++) {
			glVertex2f(
			    car1x1 + (car1radius1 * cos(car1i1 *  car1twicePi1 / car1lineAmount1)),
			    car1y1 + (car1radius1* sin(car1i1 * car1twicePi1 / car1lineAmount1))
			);
		}
	glEnd();
    glPopMatrix();




      glPushMatrix();
    glTranslatef(bus_position2,0.0f, 0.0f);

	glBegin(GL_POLYGON);
	glColor3ub(90, 99, 17);
	glVertex2f(.94f,-.70f);
	glVertex2f(.65f,-.70f);
	glVertex2f(.63f,-.80f);
	glVertex2f(.95f,-.80f);
	glVertex2f(.95f,-.73f);
	glEnd();




//////////////////////////////////////window/////////////////////



     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.665f,-.71f);
	glVertex2f(.65f,-.79f);
	glVertex2f(.73f,-.79f);
	glVertex2f(.73f,-.71f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.74f,-.71f);
	glVertex2f(.74f,-.79f);
	glVertex2f(.82f,-.79f);
	glVertex2f(.82f,-.71f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.83f,-.71f);
	glVertex2f(.83f,-.79f);
	glVertex2f(.91f,-.79f);
	glVertex2f(.91f,-.71f);
	glEnd();

///////////////////////////////////body///////////////////


      glBegin(GL_QUADS);
	glColor3ub(42, 45, 19);
	glVertex2f(.63f,-.80f);
	glVertex2f(.63f,-.88f);
	glVertex2f(.95f,-.88f);
	glVertex2f(.95f,-.80f);
	glEnd();


	//////////////////////////wheel////////////////////////

	 GLfloat bus2x=.7f; GLfloat bus2y=-.88f; GLfloat bus2radius =.025f;
	int bus2i;
	int bus2lineAmount = 100;
	GLfloat bus2twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus2i = 0; bus2i <= bus2lineAmount;bus2i++) {
			glVertex2f(
			    bus2x + (bus2radius * cos(bus2i *  bus2twicePi / bus2lineAmount)),
			    bus2y + (bus2radius* sin(bus2i * bus2twicePi / bus2lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat bus2x1=.87f; GLfloat bus2y1=-.88f; GLfloat bus2radius1 =.025f;
	int bus2i1;
	int bus2lineAmount1 = 100;
	GLfloat bus2twicePi1 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus2i1 = 0; bus2i1 <= bus2lineAmount1;bus2i1++) {
			glVertex2f(
			    bus2x1 + (bus2radius1 * cos(bus2i1 *  bus2twicePi1 / bus2lineAmount1)),
			    bus2y1 + (bus2radius1* sin(bus2i1 * bus2twicePi1 / bus2lineAmount1))
			);
		}
	glEnd();
	glPopMatrix();



	glFlush();  // Render now
}
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////













void evening(/*int value*/) {
	glClearColor(1.0f, 1.0f, 1.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);

	glLoadIdentity();
	glLineWidth(2.0);

	GLfloat x, y;
	int i;
	GLfloat radius;
	int triangleAmount = 20;
	GLfloat twicePi = 2.0f * PI;


	glBegin(GL_QUADS); //sky
	glColor3ub(186, 94, 1);
	glVertex2f(-1,1);
	glVertex2f(-1,.2);
    glVertex2f(1,.2);
    glVertex2f(1,1);
	glEnd();

	//sun
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(219, 108, 4);
        x=.75f; y=.55f; radius =.1f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();
	//moon ends

	glPushMatrix();
    glTranslatef(cloud_position1,0.0f, 0.0f);

	//cloud 01 starts
	x=-.78f;
	y=.7f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.7f;
	y=.77f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.64f;
	y=.85f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.68f;
	y=.71f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
      glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.6f;
	y=.75f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.55f;
	y=.8f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	//2nd cloud starts
	glTranslatef(0.7f, 0.07f, 0.0f);
	x=-.78f;
	y=.7f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.7f;
	y=.77f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
       glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.64f;
	y=.85f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.68f;
	y=.71f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.6f;
	y=.75f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.55f;
	y=.8f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3ub(212, 206, 234);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();
	glLoadIdentity();

	glLoadIdentity();

 glPopMatrix();


    //metro
    glBegin(GL_QUADS);
	glColor3ub(15, 15, 15);

	glVertex2f(-1.0f, 0.36f);
	glVertex2f(1.0f, 0.36f);
	glVertex2f(1.0f, 0.38f);
	glVertex2f(-1.0f, 0.38f);

	glEnd();



    glPushMatrix();
    glTranslatef(metro_position1,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.0f, 0.4f);
	glVertex2f(0.2f, 0.4f);
	glVertex2f(0.2f, 0.5f);
	glVertex2f(0.0f, 0.5f);

	glEnd();

	 glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.23f, 0.4f);
	glVertex2f(0.43f, 0.4f);
	glVertex2f(0.43f, 0.5f);
	glVertex2f(0.23f, 0.5f);

	glEnd();


	glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.46f, 0.4f);
	glVertex2f(0.66f, 0.4f);
	glVertex2f(0.66f, 0.5f);
	glVertex2f(0.46f, 0.5f);

	glEnd();


    glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.2f, 0.42f);
	glVertex2f(0.23f, 0.42f);
	glVertex2f(0.23f, 0.44f);
	glVertex2f(0.2f, 0.44f);

	glEnd();


	 glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.2f, 0.46f);
	glVertex2f(0.23f, 0.46f);
	glVertex2f(0.23f, 0.48f);
	glVertex2f(0.2f, 0.48f);

	glEnd();


	  glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.43f, 0.42f);
	glVertex2f(0.46f, 0.42f);
	glVertex2f(0.46f, 0.44f);
	glVertex2f(0.43f, 0.44f);

	glEnd();


	glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.43f, 0.46f);
	glVertex2f(0.46f, 0.46);
	glVertex2f(0.46f, 0.48f);
	glVertex2f(0.43f, 0.48f);

	glEnd();



	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.02f, 0.42f);
	glVertex2f(0.08f, 0.42);
	glVertex2f(0.08f, 0.48);
	glVertex2f(0.02f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.12f, 0.42f);
	glVertex2f(0.18f, 0.42);
	glVertex2f(0.18f, 0.48);
	glVertex2f(0.12f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.02f, 0.42f);
	glVertex2f(0.08f, 0.42);
	glVertex2f(0.08f, 0.48);
	glVertex2f(0.02f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.25f, 0.42f);
	glVertex2f(0.31f, 0.42);
	glVertex2f(0.31f, 0.48);
	glVertex2f(0.25f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.35f, 0.42f);
	glVertex2f(0.41f, 0.42);
	glVertex2f(0.41f, 0.48);
	glVertex2f(0.35f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.48f, 0.42f);
	glVertex2f(0.54f, 0.42);
	glVertex2f(0.54f, 0.48);
	glVertex2f(0.48f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(232, 228, 125);

	glVertex2f(0.58f, 0.42f);
	glVertex2f(0.64f, 0.42);
	glVertex2f(0.64f, 0.48);
	glVertex2f(0.58f, 0.48f);

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.05f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.15f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();



	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.28f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.38f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.51f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.61f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glPopMatrix();








//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


///building one

	glTranslatef(0.02f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.99f, 0.2f);
	glVertex2f(-0.96f, 0.2f);
	glVertex2f(-0.96f, 0.45f);
	glVertex2f(-0.99f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.96f, 0.2f);
	glVertex2f(-0.88f, 0.2f);
	glVertex2f(-0.88f, 0.45f);
	glVertex2f(-0.96f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.94f, 0.23f);
	glVertex2f(-0.90f, 0.23f);
	glVertex2f(-0.90f, 0.31f);
	glVertex2f(-0.94f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.94f, 0.33f);
	glVertex2f(-0.90f, 0.33f);
	glVertex2f(-0.90f, 0.41f);
	glVertex2f(-0.94f, 0.41f);

	glEnd();

	///

	///building two

	///side view
	glBegin(GL_QUADS);
	glColor3ub(7, 63, 107);

	glVertex2f(-0.86f, 0.2f);
	glVertex2f(-0.83f, 0.2f);
	glVertex2f(-0.83f, 0.35f);
	glVertex2f(-0.86f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(11, 84, 140);

	glVertex2f(-0.83f, 0.2f);
	glVertex2f(-0.75f, 0.2f);
	glVertex2f(-0.75f, 0.35f);
	glVertex2f(-0.83f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.81f, 0.23f);
	glVertex2f(-0.77f, 0.23f);
	glVertex2f(-0.77f, 0.31f);
	glVertex2f(-0.81f, 0.31f);

	glEnd();

	///

	///building three

	///side view
	glBegin(GL_QUADS);
	glColor3ub(11, 86, 20);

	glVertex2f(-0.73f, 0.2f);
	glVertex2f(-0.70f, 0.2f);
	glVertex2f(-0.70f, 0.65f);
	glVertex2f(-0.73f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(18, 124, 31);

	glVertex2f(-0.70f, 0.2f);
	glVertex2f(-0.62f, 0.2f);
	glVertex2f(-0.62f, 0.65f);
	glVertex2f(-0.70f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.23f);
	glVertex2f(-0.64f, 0.23f);
	glVertex2f(-0.64f, 0.31f);
	glVertex2f(-0.68f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.33f);
	glVertex2f(-0.64f, 0.33f);
	glVertex2f(-0.64f, 0.41f);
	glVertex2f(-0.68f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.43f);
	glVertex2f(-0.64f, 0.43f);
	glVertex2f(-0.64f, 0.51f);
	glVertex2f(-0.68f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.68f, 0.53f);
	glVertex2f(-0.64f, 0.53f);
	glVertex2f(-0.64f, 0.61f);
	glVertex2f(-0.68f, 0.61f);

	glEnd();

	///

	///building four

	///side view
	glBegin(GL_QUADS);
	glColor3ub(9, 91, 94);

	glVertex2f(-0.60f, 0.2f);
	glVertex2f(-0.57f, 0.2f);
	glVertex2f(-0.57f, 0.55f);
	glVertex2f(-0.60f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(12, 118, 122);

	glVertex2f(-0.57f, 0.2f);
	glVertex2f(-0.49f, 0.2f);
	glVertex2f(-0.49f, 0.55f);
	glVertex2f(-0.57f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.55f, 0.23f);
	glVertex2f(-0.51f, 0.23f);
	glVertex2f(-0.51f, 0.31f);
	glVertex2f(-0.55f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.55f, 0.33f);
	glVertex2f(-0.51f, 0.33f);
	glVertex2f(-0.51f, 0.41f);
	glVertex2f(-0.55f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.55f, 0.43f);
	glVertex2f(-0.51f, 0.43f);
	glVertex2f(-0.51f, 0.51f);
	glVertex2f(-0.55f, 0.51f);

	glEnd();

	///

	///building five

	///side view
	glBegin(GL_QUADS);
	glColor3ub(124, 9, 44);

	glVertex2f(-0.47f, 0.2f);
	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.44f, 0.35f);
	glVertex2f(-0.47f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(150, 13, 54);

	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.36f, 0.2f);
	glVertex2f(-0.36f, 0.35f);
	glVertex2f(-0.44f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.42f, 0.23f);
	glVertex2f(-0.38f, 0.23f);
	glVertex2f(-0.38f, 0.31f);
	glVertex2f(-0.42f, 0.31f);

	glEnd();

	///

	///building six

	///side view
	glBegin(GL_QUADS);
	glColor3ub(96, 87, 89);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(135, 124, 127);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
    glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	///building seven

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building eight

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building nine

	glTranslatef(+0.39f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(7, 63, 107);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(11, 84, 140);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	///building ten

	glTranslatef(-0.13f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building eleven

    glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(205, 216, 212);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(222, 232, 228);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building twelve

	glTranslatef(0.39f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(11, 86, 20);

	glVertex2f(-0.47f, 0.2f);
	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.44f, 0.35f);
	glVertex2f(-0.47f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(18, 124, 31);

	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.36f, 0.2f);
	glVertex2f(-0.36f, 0.35f);
	glVertex2f(-0.44f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.42f, 0.23f);
	glVertex2f(-0.38f, 0.23f);
	glVertex2f(-0.38f, 0.31f);
	glVertex2f(-0.42f, 0.31f);

	glEnd();

	///

	///building thirteen

	glTranslatef(-0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building fourteen

    glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building fifteen

	glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(9, 91, 94);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(12, 118, 122);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(255,255,0);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	glLoadIdentity();

//////////////////////////////////////////////////////////////////////////////////////////////////////////








glBegin(GL_QUADS); //upper water shade
	glColor3ub(123, 137, 147);
    glVertex2f(-1.0f, 0.18f);
    glVertex2f(1.0f, 0.18f);
    glVertex2f(1.0f, 0.2f);
    glVertex2f(-1.0f, 0.2f);
    glEnd();

    glBegin(GL_QUADS);              //water
	glColor3ub(0, 113, 167);

    glVertex2f(-1.0f, -0.5f);
    glVertex2f(1.0f, -0.5f);
	glVertex2f(1.0f, 0.18f);
    glVertex2f(-1.0f, 0.18f);
    glEnd();

//ship1
     glPushMatrix();
     glTranslatef(ship_position1,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.2f, 0.08f);
    glVertex2f(0.0f, 0.08f);
    glVertex2f(0.0f, 0.18f);
    glVertex2f(-0.2f, 0.18f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.3f, 0.18f);
    glVertex2f(-0.2f, 0.08f);
    glVertex2f(-0.2f, 0.18f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(29, 109, 155);

    glVertex2f(-0.12f, 0.18f);
    glVertex2f(-0.02f, 0.18f);
    glVertex2f(-0.02f, 0.26f);
    glVertex2f(-0.12f, 0.26f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(28, 109, 155);

    glVertex2f(-0.2f, 0.18f);
    glVertex2f(-0.12f, 0.18f);
    glVertex2f(-0.12f, 0.26f);

    glEnd();

    glBegin(GL_QUADS);          ///////window start
	glColor3ub(232, 228, 125);

    glVertex2f(-0.11f, 0.19f);
    glVertex2f(-0.08f, 0.19f);
    glVertex2f(-0.08f, 0.24f);
    glVertex2f(-0.11f, 0.24f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(-0.065f, 0.19f);
    glVertex2f(-0.035f, 0.19f);
    glVertex2f(-0.035f, 0.24f);
    glVertex2f(-0.065f, 0.24f);

    glEnd();
    glPopMatrix();

//ship1 ends




	//ship2

    glPushMatrix();
    glTranslatef(ship_position2,0.0f, 0.0f);

	glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.1f, -0.1f);
    glVertex2f(0.5f, -0.1f);
	glVertex2f(0.5f, 0.1f);
    glVertex2f(0.1f, 0.1f);

    glEnd();



    glBegin(GL_TRIANGLES);
    glColor3ub(169, 181, 183);

    glVertex2f(0.5f, -0.1f);
    glVertex2f(0.7f, 0.1f);
    glVertex2f(0.5f, 0.1f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.16f, 0.1f);
    glVertex2f(0.42f, 0.1f);
    glVertex2f(0.42f, 0.2f);
    glVertex2f(0.16f, 0.2f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.42f, 0.2f);
    glVertex2f(0.42f, 0.1f);
    glVertex2f(0.52f, 0.1f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.2f, 0.2f);
    glVertex2f(0.34f, 0.2f);
    glVertex2f(0.34f, 0.28f);
    glVertex2f(0.2f, 0.28f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.34f, 0.28f);
    glVertex2f(0.34f, 0.2f);
    glVertex2f(0.4f, 0.2f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.22f, 0.28f);
    glVertex2f(0.29f, 0.28f);
    glVertex2f(0.29f, 0.34f);
    glVertex2f(0.22f, 0.34f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.29f, 0.34f);
    glVertex2f(0.29f, 0.28f);
    glVertex2f(0.32f, 0.28f);

    glEnd();



    glBegin(GL_QUADS);     ///////window start low
	glColor3ub(232, 228, 125);

    glVertex2f(0.18f, 0.12f);
    glVertex2f(0.22f, 0.12f);
    glVertex2f(0.22f, 0.18f);
    glVertex2f(0.18f, 0.18f);

    glEnd();

      glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.24f, 0.12f);
    glVertex2f(0.28f, 0.12f);
    glVertex2f(0.28f, 0.18f);
    glVertex2f(0.24f, 0.18f);

    glEnd();


      glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.3f, 0.12f);
    glVertex2f(0.34f, 0.12f);
    glVertex2f(0.34f, 0.18f);
    glVertex2f(0.3f, 0.18f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.36f, 0.12f);
    glVertex2f(0.4f, 0.12f);
    glVertex2f(0.4f, 0.18f);
    glVertex2f(0.36f, 0.18f);

    glEnd();


     glBegin(GL_QUADS);        ///////window start 2nd low
	glColor3ub(232, 228, 125);

    glVertex2f(0.22f, 0.20f);
    glVertex2f(0.26f, 0.20f);
    glVertex2f(0.26f, 0.26f);
    glVertex2f(0.22f, 0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);

    glVertex2f(0.28f, 0.20f);
    glVertex2f(0.32f, 0.20f);
    glVertex2f(0.32f, 0.26f);
    glVertex2f(0.28f, 0.26f);

    glEnd();

    glBegin(GL_QUADS);     ///////window start top
	glColor3ub(232, 228, 125);

    glVertex2f(0.24f, 0.28f);
    glVertex2f(0.28f, 0.28f);
    glVertex2f(0.28f, 0.33f);
    glVertex2f(0.24f, 0.33f);

    glEnd();


    glPopMatrix();
    //ship2 ends






    //dandy 1

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




//dandy golla1 ends

	//moon ends




    //dandy1

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();
    //dandy1 ends

    glLoadIdentity();
    glTranslatef(0.7f,0.0f,0.0f);



    ///dandy 2

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();

    //dandy 2 golla

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




    //dandy 2 golla1 ends

    ///


    glTranslatef(-1.4f,0.0f,0.0f);



    ///dandy 3

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();

    //dandy 2 golla

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,0);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




    //dandy golla1 ends

    ///

    glLoadIdentity();


/////////////////////////////////////////////////////////////////////////////////////////////////////







glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-1.0f,-.5f);
	glVertex2f(-1.0f,-.55f);
	glVertex2f(-.8f,-.55f);
	glVertex2f(-.8f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.8f,-.5f);
	glVertex2f(-.8f,-.55f);
	glVertex2f(-.6f,-.55f);
	glVertex2f(-.6f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.6f,-.5f);
	glVertex2f(-.6f,-.55f);
	glVertex2f(-.4f,-.55f);
	glVertex2f(-.4f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.4f,-.5f);
	glVertex2f(-.4f,-.55f);
	glVertex2f(-.2f,-.55f);
	glVertex2f(-.2f,-.5f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.2f,-.5f);
	glVertex2f(-.2f,-.55f);
	glVertex2f(.0f,-.55f);
	glVertex2f(.0f,-.5f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.0f,-.5f);
	glVertex2f(.0f,-.55f);
	glVertex2f(.2f,-.55f);
	glVertex2f(.2f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.2f,-.5f);
	glVertex2f(.2f,-.55f);
	glVertex2f(.4f,-.55f);
	glVertex2f(.4f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.4f,-.5f);
	glVertex2f(.4f,-.55f);
	glVertex2f(.6f,-.55f);
	glVertex2f(.6f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.6f,-.5f);
	glVertex2f(.6f,-.55f);
	glVertex2f(.8f,-.55f);
	glVertex2f(.8f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.8f,-.5f);
	glVertex2f(.8f,-.55f);
	glVertex2f(1.0f,-.55f);
	glVertex2f(1.0f,-.5f);
	glEnd();

	//////////////////////////////////////////////////////road piller 2///////////////////////////////////////////

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-1.0f,-.95f);
	glVertex2f(-1.0f,-1.0f);
	glVertex2f(-.8f,-1.0f);
	glVertex2f(-.8f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.8f,-.95f);
	glVertex2f(-.8f,-1.0f);
	glVertex2f(-.6f,-1.0f);
	glVertex2f(-.6f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.6f,-.95f);
	glVertex2f(-.6f,-1.0f);
	glVertex2f(-.4f,-1.0f);
	glVertex2f(-.4f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.4f,-.95f);
	glVertex2f(-.4f,-1.0f);
	glVertex2f(-.2f,-1.0f);
	glVertex2f(-.2f,-.95f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.2f,-.95f);
	glVertex2f(-.2f,-1.0f);
	glVertex2f(.0f,-1.0f);
	glVertex2f(.0f,-.95f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.0f,-.95f);
	glVertex2f(.0f,-1.0f);
	glVertex2f(.2f,-1.0f);
	glVertex2f(.2f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.2f,-.95f);
	glVertex2f(.2f,-1.0f);
	glVertex2f(.4f,-1.0f);
	glVertex2f(.4f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.4f,-.95f);
	glVertex2f(.4f,-1.0f);
	glVertex2f(.6f,-1.0f);
	glVertex2f(.6f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.6f,-.95f);
	glVertex2f(.6f,-1.0f);
	glVertex2f(.8f,-1.0f);
	glVertex2f(.8f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.8f,-.95f);
	glVertex2f(.8f,-1.0f);
	glVertex2f(1.0f,-1.0f);
	glVertex2f(1.0f,-.95f);
	glEnd();

///////////////////////////////////////////main road/////////////////////

    glBegin(GL_QUADS);
	glColor3ub(122, 132, 147);
	glVertex2f(-1.0f,-.55f);
	glVertex2f(-1.0f,-.95f);
	glVertex2f(1.0f,-.95f);
	glVertex2f(1.0f,-.55f);
	glEnd();

//////////////////////////////////////road division////////////////////////




	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.8f,-.73f);
	glVertex2f(-.8f,-.75f);
	glVertex2f(-.6f,-.75f);
	glVertex2f(-.6f,-.73f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.4f,-.73f);
	glVertex2f(-.4f,-.75f);
	glVertex2f(-.2f,-.75f);
	glVertex2f(-.2f,-.73f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.0f,-.73f);
	glVertex2f(.0f,-.75f);
	glVertex2f(.2f,-.75f);
	glVertex2f(.2f,-.73f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.4f,-.73f);
	glVertex2f(.4f,-.75f);
	glVertex2f(.6f,-.75f);
	glVertex2f(.6f,-.73f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.8f,-.73f);
	glVertex2f(.8f,-.75f);
	glVertex2f(1.0f,-.75f);
	glVertex2f(1.0f,-.73f);
	glEnd();

///////////////////////////////////////////////////////////////////////bus 1///////////////////////////////////////////




     glPushMatrix();
     glTranslatef(car_position1,0.0f, 0.0f);

    glBegin(GL_POLYGON);
	glColor3ub(201, 53, 12);
	glVertex2f(-.9f,-.45f);
	glVertex2f(-.9f,-.55f);
	glVertex2f(-.5f,-.55);
	glVertex2f(-.5f,-.53f);
	glVertex2f(-.55f,-.45f);
	glEnd();

	////////////////////window
    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.87f,-.47f);
	glVertex2f(-.87f,-.53f);
	glVertex2f(-.82f,-.53f);
	glVertex2f(-.82f,-.47f);
	glEnd();

     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.80f,-.47f);
	glVertex2f(-.80f,-.53f);
	glVertex2f(-.75f,-.53f);
	glVertex2f(-.75f,-.47f);
	glEnd();


     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.73f,-.47f);
	glVertex2f(-.73f,-.53f);
	glVertex2f(-.68f,-.53f);
	glVertex2f(-.68f,-.47f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.66f,-.47f);
	glVertex2f(-.66f,-.53f);
	glVertex2f(-.61f,-.53f);
	glVertex2f(-.61f,-.47f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.59f,-.47f);
	glVertex2f(-.59f,-.53f);
	glVertex2f(-.51f,-.53f);
	glVertex2f(-.55f,-.47f);
	glEnd();


////////////////////////////////////body////////////

    glBegin(GL_QUADS);
	glColor3ub(30, 32, 145);
	glVertex2f(-.9f,-.55f);
	glVertex2f(-.9f,-.65f);
	glVertex2f(-.5f,-.65);
	glVertex2f(-.5f,-.55f);
	glEnd();

//////////////////////////////wheel1////////////////
 GLfloat bus1x=-.8f; GLfloat bus1y=-.64f; GLfloat bus1radius =.04f;
	int bus1i;
	int bus1lineAmount = 100;
	GLfloat bus1twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus1i = 0; bus1i <= bus1lineAmount;bus1i++) {
			glVertex2f(
			    bus1x + (bus1radius * cos(bus1i *  bus1twicePi / bus1lineAmount)),
			    bus1y + (bus1radius* sin(bus1i * bus1twicePi / bus1lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat bus1x2=-.6f; GLfloat bus1y2=-.64f; GLfloat bus1radius2 =.04f;
	int bus1i2;
	int bus1lineAmount2 = 100;
	GLfloat bus1twicePi2 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus1i2 = 0; bus1i2 <= bus1lineAmount2;bus1i2++) {
			glVertex2f(
			    bus1x2 + (bus1radius2 * cos(bus1i2 *  bus1twicePi2 / bus1lineAmount2)),
			    bus1y2 + (bus1radius2* sin(bus1i2 * bus1twicePi2 / bus1lineAmount2))
			);
		}
	glEnd();

	glPopMatrix();


//////////////////////////////////car///////////////////////////////////////////




    glPushMatrix();
    glTranslatef(car_position2,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(193, 211, 25);
	glVertex2f(-.06f,-.47f);
	glVertex2f(-.11f,-.53f);
	glVertex2f(.10f,-.53);
	glVertex2f(.06f,-.47f);
	glEnd();

	///////////////////////////window/////////////////

    glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(-.05f,-.48f);
	glVertex2f(-.09f,-.52f);
	glVertex2f(-.01f,-.52f);
	glVertex2f(-.01f,-.48f);
	glEnd();

     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.01f,-.48f);
	glVertex2f(.01f,-.52f);
	glVertex2f(.08f,-.52f);
	glVertex2f(.05f,-.48f);
	glEnd();

    ////////////////////////////body///////////////////

     glBegin(GL_POLYGON);
	glColor3ub(111, 119, 29);
	glVertex2f(-.11f,-.53f);
	glVertex2f(-.15f,-.55f);
	glVertex2f(-.15f,-.6f);
	glVertex2f(.16f,-.6f);
	glVertex2f(.16f,-.56f);
	glVertex2f(.10f,-.53f);
	glEnd();


	//////////////////////////////wheel1////////////////
 GLfloat car1x=-.07f; GLfloat car1y=-.6f; GLfloat car1radius =.025f;
	int car1i;
	int car1lineAmount = 100;
	GLfloat car1twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(car1i = 0; car1i <= car1lineAmount;car1i++) {
			glVertex2f(
			    car1x + (car1radius * cos(car1i *  car1twicePi / car1lineAmount)),
			    car1y + (car1radius* sin(car1i * car1twicePi / car1lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat car1x1=.07f; GLfloat car1y1=-.6f; GLfloat car1radius1 =.025f;
	int car1i1;
	int car1lineAmount1 = 100;
	GLfloat car1twicePi1 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(car1i1 = 0; car1i1 <= car1lineAmount1;car1i1++) {
			glVertex2f(
			    car1x1 + (car1radius1 * cos(car1i1 *  car1twicePi1 / car1lineAmount1)),
			    car1y1 + (car1radius1* sin(car1i1 * car1twicePi1 / car1lineAmount1))
			);
		}
	glEnd();

    glPopMatrix();
///////////////////////////////////////bus2///////////////////////////////

    glPushMatrix();
    glTranslatef(bus_position2,0.0f, 0.0f);

	glBegin(GL_POLYGON);
	glColor3ub(90, 99, 17);
	glVertex2f(.94f,-.70f);
	glVertex2f(.65f,-.70f);
	glVertex2f(.63f,-.80f);
	glVertex2f(.95f,-.80f);
	glVertex2f(.95f,-.73f);
	glEnd();




//////////////////////////////////////window/////////////////////



     glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.665f,-.71f);
	glVertex2f(.65f,-.79f);
	glVertex2f(.73f,-.79f);
	glVertex2f(.73f,-.71f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.74f,-.71f);
	glVertex2f(.74f,-.79f);
	glVertex2f(.82f,-.79f);
	glVertex2f(.82f,-.71f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(232, 228, 125);
	glVertex2f(.83f,-.71f);
	glVertex2f(.83f,-.79f);
	glVertex2f(.91f,-.79f);
	glVertex2f(.91f,-.71f);
	glEnd();

///////////////////////////////////body///////////////////


      glBegin(GL_QUADS);
	glColor3ub(42, 45, 19);
	glVertex2f(.63f,-.80f);
	glVertex2f(.63f,-.88f);
	glVertex2f(.95f,-.88f);
	glVertex2f(.95f,-.80f);
	glEnd();


	//////////////////////////wheel////////////////////////

	 GLfloat bus2x=.7f; GLfloat bus2y=-.88f; GLfloat bus2radius =.025f;
	int bus2i;
	int bus2lineAmount = 100;
	GLfloat bus2twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus2i = 0; bus2i <= bus2lineAmount;bus2i++) {
			glVertex2f(
			    bus2x + (bus2radius * cos(bus2i *  bus2twicePi / bus2lineAmount)),
			    bus2y + (bus2radius* sin(bus2i * bus2twicePi / bus2lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat bus2x1=.87f; GLfloat bus2y1=-.88f; GLfloat bus2radius1 =.025f;
	int bus2i1;
	int bus2lineAmount1 = 100;
	GLfloat bus2twicePi1 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus2i1 = 0; bus2i1 <= bus2lineAmount1;bus2i1++) {
			glVertex2f(
			    bus2x1 + (bus2radius1 * cos(bus2i1 *  bus2twicePi1 / bus2lineAmount1)),
			    bus2y1 + (bus2radius1* sin(bus2i1 * bus2twicePi1 / bus2lineAmount1))
			);
		}
	glEnd();
	glPopMatrix();

	GLfloat sx=0.0f;
	GLfloat sy=1;
	GLfloat dx=.005;
    GLfloat dy=.025;
    GLfloat px=0;
    GLfloat py=0;

    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=1; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        glColor3f(1,1,1);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();

    //rain 02
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.1f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

     //rain 03
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.2f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

     //rain 04
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.3f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 05
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.4f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 06
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.5f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 07
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.6f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 08
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.7f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 09
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.8f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 10
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(0.9f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 11
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(1.0f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

        //rain 12
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(1.1f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }

    glPopMatrix();
    glLoadIdentity();

         //rain 13
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(1.2f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

         //rain 14
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(1.3f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //------------------------------------------------------------------------------------
     //rain 15
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.1f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 16
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.2f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 16
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.3f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 17
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.4f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 18
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.5f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 19
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.6f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 20
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.7f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 21
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.8f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 22
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-.9f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();

    //rain 23
    sx=0.0f;
	sy=1;
	dx=.005;
    dy=.025;
    px=0;
    py=0;
    glTranslatef(-1.0f, 0.0f, 0.0f);
    glPushMatrix();
    glTranslatef(Rain_positionX, Rain_positionY, 0.0f);
    for(int i=0; i<=rain_count;i++)
    {
        glBegin(GL_LINES);
        px=sx+dx;
        py=sy+dy;
        glVertex2f(sx,sy);
        glVertex2f(px,py);
        sx=px+dx;
        sy=py+dy;
        glEnd();
    }
    glPopMatrix();
    glLoadIdentity();


    //glutTimerFunc(5000, night, 0);

	glFlush();  // Render now
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////






void Day() {
	glClearColor(1.0f, 1.0f, 1.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);

	glLoadIdentity();
	glLineWidth(2.0);

	GLfloat x, y;
	int i;
	GLfloat radius;
	int triangleAmount = 20;
	GLfloat twicePi = 2.0f * PI;


	glBegin(GL_QUADS); //sky
	glColor3ub(135,206,250);
	glVertex2f(-1,1);
	glVertex2f(-1,.2);
    glVertex2f(1,.2);
    glVertex2f(1,1);
	glEnd();

	//moon
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(236, 189, 44);
        x=.3f; y=.75f; radius =.1f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();
	//moon ends





	glPushMatrix();
    glTranslatef(cloud_position1,0.0f, 0.0f);

	//cloud 01 starts
	x=-.78f;
	y=.7f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.7f;
	y=.77f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.64f;
	y=.85f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.68f;
	y=.71f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.6f;
	y=.75f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.55f;
	y=.8f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	//2nd cloud starts
	glTranslatef(0.7f, 0.07f, 0.0f);
	x=-.78f;
	y=.7f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.7f;
	y=.77f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.64f;
	y=.85f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.68f;
	y=.71f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.6f;
	y=.75f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	x=-.55f;
	y=.8f;
	radius =.08f;
	glBegin(GL_TRIANGLE_FAN);
        glColor3f(1,1,1);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();
	glLoadIdentity();

	glLoadIdentity();

 glPopMatrix();

/////////////////////////////////////////////////////////////////////////////////////////////////////////

//Plane starts from here
	glPushMatrix();
    glTranslatef(plane_position,0.0f, 0.0f);
	glBegin(GL_QUADS);
	glColor3ub(226,226,226); //Aero-plane
	glVertex2f(-.8,.8);
	glVertex2f(-.8,.73);
	glVertex2f(-.65,.73);
	glVertex2f(-.65,.8);

	glVertex2f(-.8,.73);
	glVertex2f(-.8,.8);
	glVertex2f(-.85,.85);
	glVertex2f(-.85,.73);

	glColor3f(0,0,0); //window
	glVertex2f(-.79,.78);
	glVertex2f(-.79,.75);
	glVertex2f(-.77,.75);
	glVertex2f(-.77,.78);

	glVertex2f(-.71,.78);
	glVertex2f(-.71,.75);
	glVertex2f(-.69,.75);
	glVertex2f(-.69,.78);

	glColor3ub(188,188,188); //wing
	glVertex2f(-.74,.8);
	glVertex2f(-.7,.8);
	glVertex2f(-.68,.85);
	glVertex2f(-.72,.8);

	glVertex2f(-.76,.765); //wing
	glVertex2f(-.77,.72);
	glVertex2f(-.77,.71);
	glVertex2f(-.72,.765);

	glVertex2f(-.85,.765); //wing
	glVertex2f(-.86,.72);
	glVertex2f(-.86,.71);
	glVertex2f(-.81,.765);
	glEnd();

	glBegin(GL_TRIANGLES);
	glColor3ub(188,188,188);//Aero-plane
	glVertex2f(-.65,.73);
	glVertex2f(-.6,.73);
	glVertex2f(-.65,.8);
	glEnd();

	glBegin(GL_LINES);
	glColor3f(0,0,0);
	glVertex2f(-.8,.8); //plane
	glVertex2f(-.85,.8);

	glVertex2f(-.65,.8);
	glVertex2f(-.65,.73);
	glEnd();
	glPopMatrix();
	glLoadIdentity();

/////////////////////////////




    //metro
    glBegin(GL_QUADS);
	glColor3ub(15, 15, 15);

	glVertex2f(-1.0f, 0.36f);
	glVertex2f(1.0f, 0.36f);
	glVertex2f(1.0f, 0.38f);
	glVertex2f(-1.0f, 0.38f);

	glEnd();



    glPushMatrix();
    glTranslatef(metro_position1,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.0f, 0.4f);
	glVertex2f(0.2f, 0.4f);
	glVertex2f(0.2f, 0.5f);
	glVertex2f(0.0f, 0.5f);

	glEnd();

	 glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.23f, 0.4f);
	glVertex2f(0.43f, 0.4f);
	glVertex2f(0.43f, 0.5f);
	glVertex2f(0.23f, 0.5f);

	glEnd();


	glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.46f, 0.4f);
	glVertex2f(0.66f, 0.4f);
	glVertex2f(0.66f, 0.5f);
	glVertex2f(0.46f, 0.5f);

	glEnd();


    glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.2f, 0.42f);
	glVertex2f(0.23f, 0.42f);
	glVertex2f(0.23f, 0.44f);
	glVertex2f(0.2f, 0.44f);

	glEnd();


	 glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.2f, 0.46f);
	glVertex2f(0.23f, 0.46f);
	glVertex2f(0.23f, 0.48f);
	glVertex2f(0.2f, 0.48f);

	glEnd();


	  glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.43f, 0.42f);
	glVertex2f(0.46f, 0.42f);
	glVertex2f(0.46f, 0.44f);
	glVertex2f(0.43f, 0.44f);

	glEnd();


	glBegin(GL_QUADS);
	glColor3ub(255, 0, 4);

	glVertex2f(0.43f, 0.46f);
	glVertex2f(0.46f, 0.46);
	glVertex2f(0.46f, 0.48f);
	glVertex2f(0.43f, 0.48f);

	glEnd();



	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.02f, 0.42f);
	glVertex2f(0.08f, 0.42);
	glVertex2f(0.08f, 0.48);
	glVertex2f(0.02f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.12f, 0.42f);
	glVertex2f(0.18f, 0.42);
	glVertex2f(0.18f, 0.48);
	glVertex2f(0.12f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.02f, 0.42f);
	glVertex2f(0.08f, 0.42);
	glVertex2f(0.08f, 0.48);
	glVertex2f(0.02f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.25f, 0.42f);
	glVertex2f(0.31f, 0.42);
	glVertex2f(0.31f, 0.48);
	glVertex2f(0.25f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.35f, 0.42f);
	glVertex2f(0.41f, 0.42);
	glVertex2f(0.41f, 0.48);
	glVertex2f(0.35f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.48f, 0.42f);
	glVertex2f(0.54f, 0.42);
	glVertex2f(0.54f, 0.48);
	glVertex2f(0.48f, 0.48f);

	glEnd();


	glBegin(GL_QUADS);       //window
	glColor3ub(15, 15, 15);

	glVertex2f(0.58f, 0.42f);
	glVertex2f(0.64f, 0.42);
	glVertex2f(0.64f, 0.48);
	glVertex2f(0.58f, 0.48f);

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.05f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.15f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();



	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.28f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.38f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.51f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(15, 15, 15);
        x=.61f; y=.39f; radius =.02f;

	//GLfloat radius = 0.8f; //radius
	twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glPopMatrix();






//////////////////////////////////////////////////////////////////////////////////////////////////////////



///building one

	glTranslatef(0.02f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.99f, 0.2f);
	glVertex2f(-0.96f, 0.2f);
	glVertex2f(-0.96f, 0.45f);
	glVertex2f(-0.99f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.96f, 0.2f);
	glVertex2f(-0.88f, 0.2f);
	glVertex2f(-0.88f, 0.45f);
	glVertex2f(-0.96f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.94f, 0.23f);
	glVertex2f(-0.90f, 0.23f);
	glVertex2f(-0.90f, 0.31f);
	glVertex2f(-0.94f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.94f, 0.33f);
	glVertex2f(-0.90f, 0.33f);
	glVertex2f(-0.90f, 0.41f);
	glVertex2f(-0.94f, 0.41f);

	glEnd();

	///

	///building two

	///side view
	glBegin(GL_QUADS);
	glColor3ub(7, 63, 107);

	glVertex2f(-0.86f, 0.2f);
	glVertex2f(-0.83f, 0.2f);
	glVertex2f(-0.83f, 0.35f);
	glVertex2f(-0.86f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(11, 84, 140);

	glVertex2f(-0.83f, 0.2f);
	glVertex2f(-0.75f, 0.2f);
	glVertex2f(-0.75f, 0.35f);
	glVertex2f(-0.83f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.81f, 0.23f);
	glVertex2f(-0.77f, 0.23f);
	glVertex2f(-0.77f, 0.31f);
	glVertex2f(-0.81f, 0.31f);

	glEnd();

	///

	///building three

	///side view
	glBegin(GL_QUADS);
	glColor3ub(11, 86, 20);

	glVertex2f(-0.73f, 0.2f);
	glVertex2f(-0.70f, 0.2f);
	glVertex2f(-0.70f, 0.65f);
	glVertex2f(-0.73f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(18, 124, 31);

	glVertex2f(-0.70f, 0.2f);
	glVertex2f(-0.62f, 0.2f);
	glVertex2f(-0.62f, 0.65f);
	glVertex2f(-0.70f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.68f, 0.23f);
	glVertex2f(-0.64f, 0.23f);
	glVertex2f(-0.64f, 0.31f);
	glVertex2f(-0.68f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.68f, 0.33f);
	glVertex2f(-0.64f, 0.33f);
	glVertex2f(-0.64f, 0.41f);
	glVertex2f(-0.68f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.68f, 0.43f);
	glVertex2f(-0.64f, 0.43f);
	glVertex2f(-0.64f, 0.51f);
	glVertex2f(-0.68f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.68f, 0.53f);
	glVertex2f(-0.64f, 0.53f);
	glVertex2f(-0.64f, 0.61f);
	glVertex2f(-0.68f, 0.61f);

	glEnd();

	///

	///building four

	///side view
	glBegin(GL_QUADS);
	glColor3ub(9, 91, 94);

	glVertex2f(-0.60f, 0.2f);
	glVertex2f(-0.57f, 0.2f);
	glVertex2f(-0.57f, 0.55f);
	glVertex2f(-0.60f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(12, 118, 122);

	glVertex2f(-0.57f, 0.2f);
	glVertex2f(-0.49f, 0.2f);
	glVertex2f(-0.49f, 0.55f);
	glVertex2f(-0.57f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.55f, 0.23f);
	glVertex2f(-0.51f, 0.23f);
	glVertex2f(-0.51f, 0.31f);
	glVertex2f(-0.55f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.55f, 0.33f);
	glVertex2f(-0.51f, 0.33f);
	glVertex2f(-0.51f, 0.41f);
	glVertex2f(-0.55f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.55f, 0.43f);
	glVertex2f(-0.51f, 0.43f);
	glVertex2f(-0.51f, 0.51f);
	glVertex2f(-0.55f, 0.51f);

	glEnd();

	///

	///building five

	///side view
	glBegin(GL_QUADS);
	glColor3ub(124, 9, 44);

	glVertex2f(-0.47f, 0.2f);
	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.44f, 0.35f);
	glVertex2f(-0.47f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(150, 13, 54);

	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.36f, 0.2f);
	glVertex2f(-0.36f, 0.35f);
	glVertex2f(-0.44f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.42f, 0.23f);
	glVertex2f(-0.38f, 0.23f);
	glVertex2f(-0.38f, 0.31f);
	glVertex2f(-0.42f, 0.31f);

	glEnd();

	///

	///building six

	///side view
	glBegin(GL_QUADS);
	glColor3ub(96, 87, 89);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(135, 124, 127);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	///building seven

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building eight

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building nine

	glTranslatef(+0.39f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(7, 63, 107);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(11, 84, 140);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	///building ten

	glTranslatef(-0.13f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building eleven

    glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(205, 216, 212);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(222, 232, 228);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building twelve

	glTranslatef(0.39f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(11, 86, 20);

	glVertex2f(-0.47f, 0.2f);
	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.44f, 0.35f);
	glVertex2f(-0.47f, 0.31f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(18, 124, 31);

	glVertex2f(-0.44f, 0.2f);
	glVertex2f(-0.36f, 0.2f);
	glVertex2f(-0.36f, 0.35f);
	glVertex2f(-0.44f, 0.35f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.42f, 0.23f);
	glVertex2f(-0.38f, 0.23f);
	glVertex2f(-0.38f, 0.31f);
	glVertex2f(-0.42f, 0.31f);

	glEnd();

	///

	///building thirteen

	glTranslatef(-0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(46, 94, 77);

	glVertex2f(-0.08f, 0.2f);
	glVertex2f(-0.05f, 0.2f);
	glVertex2f(-0.05f, 0.55f);
	glVertex2f(-0.08f, 0.51f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(67, 135, 111);

	glVertex2f(-0.05f, 0.2f);
	glVertex2f( 0.03f, 0.2f);
	glVertex2f( 0.03f, 0.55f);
	glVertex2f(-0.05f, 0.55f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.23f);
	glVertex2f( 0.01f, 0.23f);
	glVertex2f( 0.01f, 0.31f);
	glVertex2f(-0.03f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.33f);
	glVertex2f( 0.01f, 0.33f);
	glVertex2f( 0.01f, 0.41f);
	glVertex2f(-0.03f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.03f, 0.43f);
	glVertex2f( 0.01f, 0.43f);
	glVertex2f( 0.01f, 0.51f);
	glVertex2f(-0.03f, 0.51f);

	glEnd();

	///

	///building fourteen

    glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(183, 68, 14);

	glVertex2f(-0.21f, 0.2f);
	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.18f, 0.45f);
	glVertex2f(-0.21f, 0.41f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(224, 86, 22);

	glVertex2f(-0.18f, 0.2f);
	glVertex2f(-0.10f, 0.2f);
	glVertex2f(-0.10f, 0.45f);
	glVertex2f(-0.18f, 0.45f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.16f, 0.23f);
	glVertex2f(-0.12f, 0.23f);
	glVertex2f(-0.12f, 0.31f);
	glVertex2f(-0.16f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.16f, 0.33f);
	glVertex2f(-0.12f, 0.33f);
	glVertex2f(-0.12f, 0.41f);
	glVertex2f(-0.16f, 0.41f);

	glEnd();

	///

	///building fifteen

	glTranslatef(+0.26f,0.0f,0.0f);

	///side view
	glBegin(GL_QUADS);
	glColor3ub(9, 91, 94);

	glVertex2f(-0.34f, 0.2f);
	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.31f, 0.65f);
	glVertex2f(-0.34f, 0.61f);

	glEnd();

	///front view
	glBegin(GL_QUADS);
	glColor3ub(12, 118, 122);

	glVertex2f(-0.31f, 0.2f);
	glVertex2f(-0.23f, 0.2f);
	glVertex2f(-0.23f, 0.65f);
	glVertex2f(-0.31f, 0.65f);

	glEnd();

	///window one

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.23f);
	glVertex2f(-0.25f, 0.23f);
	glVertex2f(-0.25f, 0.31f);
	glVertex2f(-0.29f, 0.31f);

	glEnd();

	///window two

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.33f);
	glVertex2f(-0.25f, 0.33f);
	glVertex2f(-0.25f, 0.41f);
	glVertex2f(-0.29f, 0.41f);

	glEnd();

	///window three

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.43f);
	glVertex2f(-0.25f, 0.43f);
	glVertex2f(-0.25f, 0.51f);
	glVertex2f(-0.29f, 0.51f);

	glEnd();

	///window four

	glBegin(GL_QUADS);
	glColor3ub(51, 36, 29);

	glVertex2f(-0.29f, 0.53f);
	glVertex2f(-0.25f, 0.53f);
	glVertex2f(-0.25f, 0.61f);
	glVertex2f(-0.29f, 0.61f);

	glEnd();

	///

	glLoadIdentity();

//////////////////////////////////////////////////////////////////////////////////////////////////////////








glBegin(GL_QUADS); //upper water shade
	glColor3ub(123, 137, 147);
    glVertex2f(-1.0f, 0.18f);
    glVertex2f(1.0f, 0.18f);
    glVertex2f(1.0f, 0.2f);
    glVertex2f(-1.0f, 0.2f);
    glEnd();

    glBegin(GL_QUADS);              //water
	glColor3ub(192, 214, 249);

    glVertex2f(-1.0f, -0.5f);
    glVertex2f(1.0f, -0.5f);
	glVertex2f(1.0f, 0.18f);
    glVertex2f(-1.0f, 0.18f);
    glEnd();



//ship1
     glPushMatrix();
     glTranslatef(ship_position1,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.2f, 0.08f);
    glVertex2f(0.0f, 0.08f);
    glVertex2f(0.0f, 0.18f);
    glVertex2f(-0.2f, 0.18f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.3f, 0.18f);
    glVertex2f(-0.2f, 0.08f);
    glVertex2f(-0.2f, 0.18f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(29, 109, 155);

    glVertex2f(-0.12f, 0.18f);
    glVertex2f(-0.02f, 0.18f);
    glVertex2f(-0.02f, 0.26f);
    glVertex2f(-0.12f, 0.26f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(28, 109, 155);

    glVertex2f(-0.2f, 0.18f);
    glVertex2f(-0.12f, 0.18f);
    glVertex2f(-0.12f, 0.26f);

    glEnd();

    glBegin(GL_QUADS);          ///////window start
	glColor3ub(169, 181, 183);

    glVertex2f(-0.11f, 0.19f);
    glVertex2f(-0.08f, 0.19f);
    glVertex2f(-0.08f, 0.24f);
    glVertex2f(-0.11f, 0.24f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(-0.065f, 0.19f);
    glVertex2f(-0.035f, 0.19f);
    glVertex2f(-0.035f, 0.24f);
    glVertex2f(-0.065f, 0.24f);

    glEnd();
    glPopMatrix();

//ship1 ends




	//ship2

    glPushMatrix();
    glTranslatef(ship_position2,0.0f, 0.0f);

	glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.1f, -0.1f);
    glVertex2f(0.5f, -0.1f);
	glVertex2f(0.5f, 0.1f);
    glVertex2f(0.1f, 0.1f);

    glEnd();



    glBegin(GL_TRIANGLES);
    glColor3ub(169, 181, 183);

    glVertex2f(0.5f, -0.1f);
    glVertex2f(0.7f, 0.1f);
    glVertex2f(0.5f, 0.1f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.16f, 0.1f);
    glVertex2f(0.42f, 0.1f);
    glVertex2f(0.42f, 0.2f);
    glVertex2f(0.16f, 0.2f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.42f, 0.2f);
    glVertex2f(0.42f, 0.1f);
    glVertex2f(0.52f, 0.1f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.2f, 0.2f);
    glVertex2f(0.34f, 0.2f);
    glVertex2f(0.34f, 0.28f);
    glVertex2f(0.2f, 0.28f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.34f, 0.28f);
    glVertex2f(0.34f, 0.2f);
    glVertex2f(0.4f, 0.2f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(26, 102, 255);

    glVertex2f(0.22f, 0.28f);
    glVertex2f(0.29f, 0.28f);
    glVertex2f(0.29f, 0.34f);
    glVertex2f(0.22f, 0.34f);

    glEnd();

     glBegin(GL_TRIANGLES);
	glColor3ub(26, 102, 255);

    glVertex2f(0.29f, 0.34f);
    glVertex2f(0.29f, 0.28f);
    glVertex2f(0.32f, 0.28f);

    glEnd();



    glBegin(GL_QUADS);     ///////window start low
	glColor3ub(169, 181, 183);

    glVertex2f(0.18f, 0.12f);
    glVertex2f(0.22f, 0.12f);
    glVertex2f(0.22f, 0.18f);
    glVertex2f(0.18f, 0.18f);

    glEnd();

      glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.24f, 0.12f);
    glVertex2f(0.28f, 0.12f);
    glVertex2f(0.28f, 0.18f);
    glVertex2f(0.24f, 0.18f);

    glEnd();


      glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.3f, 0.12f);
    glVertex2f(0.34f, 0.12f);
    glVertex2f(0.34f, 0.18f);
    glVertex2f(0.3f, 0.18f);

    glEnd();

    glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.36f, 0.12f);
    glVertex2f(0.4f, 0.12f);
    glVertex2f(0.4f, 0.18f);
    glVertex2f(0.36f, 0.18f);

    glEnd();


     glBegin(GL_QUADS);        ///////window start 2nd low
	glColor3ub(169, 181, 183);

    glVertex2f(0.22f, 0.20f);
    glVertex2f(0.26f, 0.20f);
    glVertex2f(0.26f, 0.26f);
    glVertex2f(0.22f, 0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(169, 181, 183);

    glVertex2f(0.28f, 0.20f);
    glVertex2f(0.32f, 0.20f);
    glVertex2f(0.32f, 0.26f);
    glVertex2f(0.28f, 0.26f);

    glEnd();

    glBegin(GL_QUADS);     ///////window start top
	glColor3ub(169, 181, 183);

    glVertex2f(0.24f, 0.28f);
    glVertex2f(0.28f, 0.28f);
    glVertex2f(0.28f, 0.33f);
    glVertex2f(0.24f, 0.33f);

    glEnd();


    glPopMatrix();
    //ship2 ends




    //dandy 1

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




//dandy golla1 ends

	//moon ends




    //dandy1

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();
    //dandy1 ends

    glLoadIdentity();
    glTranslatef(0.7f,0.0f,0.0f);



    ///dandy 2

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();

    //dandy 2 golla

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




    //dandy 2 golla1 ends

    ///


    glTranslatef(-1.4f,0.0f,0.0f);



    ///dandy 3

    glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.01f, -0.5f);
    glVertex2f(0.01f, -0.5f);
    glVertex2f(0.01f, -0.2f);
    glVertex2f(-0.01f, -0.2f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.1f, -0.32f);
    glVertex2f(-0.1f, -0.32f);

    glEnd();


     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(-0.1f, -0.3f);
    glVertex2f(-0.09f, -0.3f);
    glVertex2f(-0.09f, -0.26f);
    glVertex2f(-0.1f, -0.26f);

    glEnd();

     glBegin(GL_QUADS);
	glColor3ub(12, 12, 12);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.09f, -0.3f);
    glVertex2f(0.09f, -0.26f);
    glVertex2f(0.1f, -0.26f);

    glEnd();

    //dandy 2 golla

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=.0f;  y=-.15f;  radius =.05f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();


	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();

	glBegin(GL_TRIANGLE_FAN);
		glColor3ub(245, 243, 206);
			 x=-.095f;  y=-.23f;  radius =.035f;
	  triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	 twicePi = 2.0f * PI;

				glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}

	glEnd();




    //dandy golla1 ends

    ///

    glLoadIdentity();


/////////////////////////////////////////////////////////////////////////////////////////////////////







glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-1.0f,-.5f);
	glVertex2f(-1.0f,-.55f);
	glVertex2f(-.8f,-.55f);
	glVertex2f(-.8f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.8f,-.5f);
	glVertex2f(-.8f,-.55f);
	glVertex2f(-.6f,-.55f);
	glVertex2f(-.6f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.6f,-.5f);
	glVertex2f(-.6f,-.55f);
	glVertex2f(-.4f,-.55f);
	glVertex2f(-.4f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.4f,-.5f);
	glVertex2f(-.4f,-.55f);
	glVertex2f(-.2f,-.55f);
	glVertex2f(-.2f,-.5f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.2f,-.5f);
	glVertex2f(-.2f,-.55f);
	glVertex2f(.0f,-.55f);
	glVertex2f(.0f,-.5f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.0f,-.5f);
	glVertex2f(.0f,-.55f);
	glVertex2f(.2f,-.55f);
	glVertex2f(.2f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.2f,-.5f);
	glVertex2f(.2f,-.55f);
	glVertex2f(.4f,-.55f);
	glVertex2f(.4f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.4f,-.5f);
	glVertex2f(.4f,-.55f);
	glVertex2f(.6f,-.55f);
	glVertex2f(.6f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.6f,-.5f);
	glVertex2f(.6f,-.55f);
	glVertex2f(.8f,-.55f);
	glVertex2f(.8f,-.5f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.8f,-.5f);
	glVertex2f(.8f,-.55f);
	glVertex2f(1.0f,-.55f);
	glVertex2f(1.0f,-.5f);
	glEnd();

	//////////////////////////////////////////////////////road piller 2///////////////////////////////////////////

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-1.0f,-.95f);
	glVertex2f(-1.0f,-1.0f);
	glVertex2f(-.8f,-1.0f);
	glVertex2f(-.8f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.8f,-.95f);
	glVertex2f(-.8f,-1.0f);
	glVertex2f(-.6f,-1.0f);
	glVertex2f(-.6f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.6f,-.95f);
	glVertex2f(-.6f,-1.0f);
	glVertex2f(-.4f,-1.0f);
	glVertex2f(-.4f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(-.4f,-.95f);
	glVertex2f(-.4f,-1.0f);
	glVertex2f(-.2f,-1.0f);
	glVertex2f(-.2f,-.95f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.2f,-.95f);
	glVertex2f(-.2f,-1.0f);
	glVertex2f(.0f,-1.0f);
	glVertex2f(.0f,-.95f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.0f,-.95f);
	glVertex2f(.0f,-1.0f);
	glVertex2f(.2f,-1.0f);
	glVertex2f(.2f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.2f,-.95f);
	glVertex2f(.2f,-1.0f);
	glVertex2f(.4f,-1.0f);
	glVertex2f(.4f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.4f,-.95f);
	glVertex2f(.4f,-1.0f);
	glVertex2f(.6f,-1.0f);
	glVertex2f(.6f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.6f,-.95f);
	glVertex2f(.6f,-1.0f);
	glVertex2f(.8f,-1.0f);
	glVertex2f(.8f,-.95f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(.0f,.0f,.0f);
	glVertex2f(.8f,-.95f);
	glVertex2f(.8f,-1.0f);
	glVertex2f(1.0f,-1.0f);
	glVertex2f(1.0f,-.95f);
	glEnd();

///////////////////////////////////////////main road/////////////////////

    glBegin(GL_QUADS);
	glColor3ub(122, 132, 147);
	glVertex2f(-1.0f,-.55f);
	glVertex2f(-1.0f,-.95f);
	glVertex2f(1.0f,-.95f);
	glVertex2f(1.0f,-.55f);
	glEnd();

//////////////////////////////////////road division////////////////////////




	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.8f,-.73f);
	glVertex2f(-.8f,-.75f);
	glVertex2f(-.6f,-.75f);
	glVertex2f(-.6f,-.73f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(-.4f,-.73f);
	glVertex2f(-.4f,-.75f);
	glVertex2f(-.2f,-.75f);
	glVertex2f(-.2f,-.73f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.0f,-.73f);
	glVertex2f(.0f,-.75f);
	glVertex2f(.2f,-.75f);
	glVertex2f(.2f,-.73f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.4f,-.73f);
	glVertex2f(.4f,-.75f);
	glVertex2f(.6f,-.75f);
	glVertex2f(.6f,-.73f);
	glEnd();

    glBegin(GL_QUADS);
	glColor3f(1.0f,1.0f,1.0f);
	glVertex2f(.8f,-.73f);
	glVertex2f(.8f,-.75f);
	glVertex2f(1.0f,-.75f);
	glVertex2f(1.0f,-.73f);
	glEnd();

///////////////////////////////////////////////////////////////////////bus 1///////////////////////////////////////////




     glPushMatrix();
     glTranslatef(car_position1,0.0f, 0.0f);

    glBegin(GL_POLYGON);
	glColor3ub(201, 53, 12);
	glVertex2f(-.9f,-.45f);
	glVertex2f(-.9f,-.55f);
	glVertex2f(-.5f,-.55);
	glVertex2f(-.5f,-.53f);
	glVertex2f(-.55f,-.45f);
	glEnd();

	////////////////////window
    glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(-.87f,-.47f);
	glVertex2f(-.87f,-.53f);
	glVertex2f(-.82f,-.53f);
	glVertex2f(-.82f,-.47f);
	glEnd();

     glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(-.80f,-.47f);
	glVertex2f(-.80f,-.53f);
	glVertex2f(-.75f,-.53f);
	glVertex2f(-.75f,-.47f);
	glEnd();


     glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(-.73f,-.47f);
	glVertex2f(-.73f,-.53f);
	glVertex2f(-.68f,-.53f);
	glVertex2f(-.68f,-.47f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(-.66f,-.47f);
	glVertex2f(-.66f,-.53f);
	glVertex2f(-.61f,-.53f);
	glVertex2f(-.61f,-.47f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(-.59f,-.47f);
	glVertex2f(-.59f,-.53f);
	glVertex2f(-.51f,-.53f);
	glVertex2f(-.55f,-.47f);
	glEnd();


////////////////////////////////////body////////////

    glBegin(GL_QUADS);
	glColor3ub(30, 32, 145);
	glVertex2f(-.9f,-.55f);
	glVertex2f(-.9f,-.65f);
	glVertex2f(-.5f,-.65);
	glVertex2f(-.5f,-.55f);
	glEnd();

//////////////////////////////wheel1////////////////
 GLfloat bus1x=-.8f; GLfloat bus1y=-.64f; GLfloat bus1radius =.04f;
	int bus1i;
	int bus1lineAmount = 100;
	GLfloat bus1twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus1i = 0; bus1i <= bus1lineAmount;bus1i++) {
			glVertex2f(
			    bus1x + (bus1radius * cos(bus1i *  bus1twicePi / bus1lineAmount)),
			    bus1y + (bus1radius* sin(bus1i * bus1twicePi / bus1lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat bus1x2=-.6f; GLfloat bus1y2=-.64f; GLfloat bus1radius2 =.04f;
	int bus1i2;
	int bus1lineAmount2 = 100;
	GLfloat bus1twicePi2 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus1i2 = 0; bus1i2 <= bus1lineAmount2;bus1i2++) {
			glVertex2f(
			    bus1x2 + (bus1radius2 * cos(bus1i2 *  bus1twicePi2 / bus1lineAmount2)),
			    bus1y2 + (bus1radius2* sin(bus1i2 * bus1twicePi2 / bus1lineAmount2))
			);
		}
	glEnd();

	glPopMatrix();


//////////////////////////////////car///////////////////////////////////////////




    glPushMatrix();
    glTranslatef(car_position2,0.0f, 0.0f);

    glBegin(GL_QUADS);
	glColor3ub(193, 211, 25);
	glVertex2f(-.06f,-.47f);
	glVertex2f(-.11f,-.53f);
	glVertex2f(.10f,-.53);
	glVertex2f(.06f,-.47f);
	glEnd();

	///////////////////////////window/////////////////

    glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(-.05f,-.48f);
	glVertex2f(-.09f,-.52f);
	glVertex2f(-.01f,-.52f);
	glVertex2f(-.01f,-.48f);
	glEnd();

     glBegin(GL_QUADS);
	glColor3ub(41, 181, 206);
	glVertex2f(.01f,-.48f);
	glVertex2f(.01f,-.52f);
	glVertex2f(.08f,-.52f);
	glVertex2f(.05f,-.48f);
	glEnd();

    ////////////////////////////body///////////////////

     glBegin(GL_POLYGON);
	glColor3ub(111, 119, 29);
	glVertex2f(-.11f,-.53f);
	glVertex2f(-.15f,-.55f);
	glVertex2f(-.15f,-.6f);
	glVertex2f(.16f,-.6f);
	glVertex2f(.16f,-.56f);
	glVertex2f(.10f,-.53f);
	glEnd();


	//////////////////////////////wheel1////////////////
 GLfloat car1x=-.07f; GLfloat car1y=-.6f; GLfloat car1radius =.025f;
	int car1i;
	int car1lineAmount = 100;
	GLfloat car1twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(car1i = 0; car1i <= car1lineAmount;car1i++) {
			glVertex2f(
			    car1x + (car1radius * cos(car1i *  car1twicePi / car1lineAmount)),
			    car1y + (car1radius* sin(car1i * car1twicePi / car1lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat car1x1=.07f; GLfloat car1y1=-.6f; GLfloat car1radius1 =.025f;
	int car1i1;
	int car1lineAmount1 = 100;
	GLfloat car1twicePi1 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(car1i1 = 0; car1i1 <= car1lineAmount1;car1i1++) {
			glVertex2f(
			    car1x1 + (car1radius1 * cos(car1i1 *  car1twicePi1 / car1lineAmount1)),
			    car1y1 + (car1radius1* sin(car1i1 * car1twicePi1 / car1lineAmount1))
			);
		}
	glEnd();

    glPopMatrix();
glLoadIdentity();


    glPushMatrix();
    glTranslatef(bus_position2,0.0f, 0.0f);

	glBegin(GL_POLYGON);
	glColor3ub(90, 99, 17);
	glVertex2f(.94f,-.70f);
	glVertex2f(.65f,-.70f);
	glVertex2f(.63f,-.80f);
	glVertex2f(.95f,-.80f);
	glVertex2f(.95f,-.73f);
	glEnd();




//////////////////////////////////////window/////////////////////



     glBegin(GL_QUADS);
	glColor3ub(15, 244, 252);
	glVertex2f(.665f,-.71f);
	glVertex2f(.65f,-.79f);
	glVertex2f(.73f,-.79f);
	glVertex2f(.73f,-.71f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(15, 244, 252);
	glVertex2f(.74f,-.71f);
	glVertex2f(.74f,-.79f);
	glVertex2f(.82f,-.79f);
	glVertex2f(.82f,-.71f);
	glEnd();

	glBegin(GL_QUADS);
	glColor3ub(15, 244, 252);
	glVertex2f(.83f,-.71f);
	glVertex2f(.83f,-.79f);
	glVertex2f(.91f,-.79f);
	glVertex2f(.91f,-.71f);
	glEnd();

///////////////////////////////////body///////////////////


      glBegin(GL_QUADS);
	glColor3ub(42, 45, 19);
	glVertex2f(.63f,-.80f);
	glVertex2f(.63f,-.88f);
	glVertex2f(.95f,-.88f);
	glVertex2f(.95f,-.80f);
	glEnd();


	//////////////////////////wheel////////////////////////

	 GLfloat bus2x=.7f; GLfloat bus2y=-.88f; GLfloat bus2radius =.025f;
	int bus2i;
	int bus2lineAmount = 100;
	GLfloat bus2twicePi = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus2i = 0; bus2i <= bus2lineAmount;bus2i++) {
			glVertex2f(
			    bus2x + (bus2radius * cos(bus2i *  bus2twicePi / bus2lineAmount)),
			    bus2y + (bus2radius* sin(bus2i * bus2twicePi / bus2lineAmount))
			);
		}
	glEnd();

////////////////////////////////wheel2///////////////////////////
 GLfloat bus2x1=.87f; GLfloat bus2y1=-.88f; GLfloat bus2radius1 =.025f;
	int bus2i1;
	int bus2lineAmount1 = 100;
	GLfloat bus2twicePi1 = 2.0f * PI;
	glBegin(GL_TRIANGLE_FAN);
	glColor3ub(2, 2, 2);
		for(bus2i1 = 0; bus2i1 <= bus2lineAmount1;bus2i1++) {
			glVertex2f(
			    bus2x1 + (bus2radius1 * cos(bus2i1 *  bus2twicePi1 / bus2lineAmount1)),
			    bus2y1 + (bus2radius1* sin(bus2i1 * bus2twicePi1 / bus2lineAmount1))
			);
		}
	glEnd();
	glPopMatrix();

//glutTimerFunc(5000, evening, 0);
//glutTimerFunc(500, Rain_update, 0);


	glFlush();  // Render now
}


//////////////////////////////////////////////////////////////////////////////////////////////////////////













/* Main function: GLUT runs as a console application starting at main()  */

void SpecialInput(int key, int x, int y)
{
switch(key)
{
case GLUT_KEY_UP:
    glutTimerFunc(100, Plane_update, 0);
    plane_speed = 0.05f;

 glutTimerFunc(100, cloud_update1, 0);
 cloud_speed = 0.01f;

 glutTimerFunc(100, ship_update1, 0);
 ship_speed1 = 0.01f;

 glutTimerFunc(100, ship_update2, 0);
 ship_speed2 = 0.01f;

 glutTimerFunc(100, car_update1, 0);
 car_speed1 = 0.01f;

 glutTimerFunc(100, car_update2, 0);
 car_speed2 = 0.01f;

 glutTimerFunc(100, bus_update2, 0);
 bus_speed2 = 0.01f;

 glutTimerFunc(100, metro_update1, 0);
 metro_speed1 = 0.01f;
 PlaySound("sound.wav", NULL, SND_ASYNC|SND_LOOP);

break;
case GLUT_KEY_DOWN:

 cloud_speed = 0.00f;
 ship_speed1 = 0.00f;
 ship_speed2 = 0.00f;
 car_speed1 = 0.00f;
 car_speed2 = 0.00f;
 bus_speed2 = 0.00f;
 metro_speed1 = 0.00f;
 plane_speed = 0.00f;
break;

case GLUT_KEY_LEFT:

//    if(car_speed1<=-.01)
//    {
//        cloud_speed = 0.01f;
//        ship_speed1 = 0.01f;
//        ship_speed2 = 0.01f;
//        car_speed1 = 0.01f;
//        car_speed2 = 0.01f;
//        bus_speed2 = 0.01f;
//        metro_speed1 = 0.01f;
//    }
//    else
//    {
//        cloud_speed -= 0.005f;
//         ship_speed1 -=  0.005f;
//         ship_speed2 -=  0.005f;
//         car_speed1 -=  0.005f;
//         car_speed2 -=  0.005f;
//         bus_speed2 -=  0.005f;
//         metro_speed1 -=  0.005f;
//    }
//    if(plane_speed<=.02)
//    {
//        plane_speed -=  0.01f;
//    }
//    else
//    {
//        plane_speed -=  0.005f;
//    }

break;
case GLUT_KEY_RIGHT:

break;
}
glutPostRedisplay();
}

void handleKeypress(unsigned char key, int x, int y) {

	switch (key) {

case 'd':
    glutDisplayFunc(Day);
    glutPostRedisplay();
    PlaySound("sound.wav", NULL, SND_ASYNC|SND_LOOP);
    break;
case 'e':
    glutDisplayFunc(evening);
    glutTimerFunc(20, Rain_update, 0);
    glutPostRedisplay();
     PlaySound("test.wav", NULL, SND_ASYNC|SND_LOOP);
    break;

case 'n':
    glutDisplayFunc(night);
    glutPostRedisplay();
    PlaySound("sound.wav", NULL, SND_ASYNC|SND_LOOP);
    break;
	}
	glutPostRedisplay();
}

//void View_update(int value) {
//
//    if(mode==0)
//    {
//        glutDisplayFunc(Day);
//        glutPostRedisplay();
//        mode=1;
//    }
//    else if(mode==1)
//    {
//        glutDisplayFunc(evening);
//        glutPostRedisplay();
//        mode=2;
//    }
//     else if(mode==2)
//    {
//        glutDisplayFunc(night);
//        glutPostRedisplay();
//        mode=0;
//    }
//
//
//     glutPostRedisplay();
//	glutTimerFunc(5000, View_update, 0);
//}



int main(int argc, char** argv) {
	glutInit(&argc, argv);                 // Initialize GLUT
	glutCreateWindow("OpenGL Setup"); // Create a window with the given title
	glutInitWindowSize(320, 320);   // Set the window's initial width & height
	glutDisplayFunc(Day);
    //initGL();
    glutIdleFunc(Idle);// Register display callback handler for window re-paint
    //glutTimerFunc(100, update, 0);
    //glutTimerFunc(100, update1, 0);
	           // Enter the event-processing loop


   glutInitWindowPosition(50, 50);
  // glutCreateWindow("Basic Animation");
   init();

   //glutTimerFunc(5000, View_update, 0);
   glutSpecialFunc(SpecialInput);
   glutKeyboardFunc(handleKeypress);
   glutMainLoop();


	return 0;

}

