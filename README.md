# courseadviserapp-ToastyKrabstix
This assignment illustrates the usage of a Spinner widget and a simple Button.

## Problem:

Design and implement an Android application that gives suggestions to a 1st / 2nd year regular student about the available courses for him/her to take.

## Data Structure:

```Java
List<String> courses = new ArrayList<String>();

        if (term.equals("1st term")) {
            courses.add("NSTP101");
            courses.add("PERSEF1");
            courses.add("LASARE1");
            courses.add("FITWELL");
            courses.add("ENGALG1");
            courses.add("ENGTRIG");
            courses.add("ENGLCOM");
            courses.add("FILKOMU");
            courses.add("TREDONE");
            courses.add("GRAPONE");
        }

        else if (term.equals("2nd term")) {
            courses.add("NSTP-R1/C1");
            courses.add("FTSPORT");
            courses.add("ANAGEOM");
            courses.add("SOLIMEN");
            courses.add("DIFFCAL");
            courses.add("ENGLRES");
            courses.add("FILDLAR");
            courses.add("CHEMONE");
            courses.add("LBYCH11");
        }
        else if (term.equals("3rd term")) {
            courses.add("SAS1000");
            courses.add("NSTP-R2/C2");
            courses.add("FTDANCE");
            courses.add("INTECAL");
            courses.add("ENGALG2");
            courses.add("SPEECOM");
            courses.add("SOCTEC1");
            courses.add("LBYMEEA");
            courses.add("ENGPHY1");
            courses.add("LPYPH11");
        }
        else if (term.equals("4th term")) {
            courses.add("HUMALIT");
            courses.add("KASPIL1");
            courses.add("STATICS");
            courses.add("ENGIANA");
            courses.add("ENGPHY2");
            courses.add("LBYPH12");
            courses.add("FTTEAMS");
            courses.add("LBYEC71");
        }
        else if (term.equals("5th term")) {
            courses.add("HUMAART");
            courses.add("TREDTWO");
            courses.add("DYNAMIC");
            courses.add("ENGSTAT");
            courses.add("DISMATH");
            courses.add("ELCIAN1");
            courses.add("LBYEC11");
            courses.add("LBYEC72");
            courses.add("LASARE2");
        }
        else { // 6th term
            courses.add("MEDEFOR");
            courses.add("ENVIRON");
            courses.add("CONTSIG");
            courses.add("VECANAL");
            courses.add("ELCIAN2");
            courses.add("LBYEC12");
            courses.add("ELETRO1");
            courses.add("LBYEC13");
        }
        return courses;
```



## Keypoints:

In the MainActivity.java:

```Java
public void onClickFindCourse(View view){
        //Get a reference to the Spinner
        Spinner spinner = (Spinner) findViewById(R.id.spinner_terms);

        //Get a reference to the TextView
        TextView courses = (TextView) findViewById(R.id.tv_courses);

        //Get the selected item in the Spinner
        String term = String.valueOf(spinner.getSelectedItem());

        //Get recommendations from the Course Checklist
        List<String> courseList = coursechecklist.getCourses(term);

        //Format string list
        StringBuilder coursesFormatted = new StringBuilder();

        for (String course: courseList)
            coursesFormatted.append(course).append('\n');

        //Display the selected item
        courses.setText(coursesFormatted);
    }
```


In the layout xml file for Button widget
```xml
<Button
        android:id="@+id/button_course"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_below="@+id/spinner_terms"
        android:text="@string/find_course"
        android:onClick="onClickFindCourse"/>
```


In the layout xml file for Spinner widget

```xml
<Spinner
        android:id="@+id/spinner_terms"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="38dp"
        android:entries="@array/terms"/>
```

In the 'strings.xml' for array (utilized by the Spinner)

```xml
<string-array name="terms">
        <item>1st term</item>
        <item>2nd term</item>
        <item>3rd term</item>
        <item>4th term</item>
        <item>5th term</item>
        <item>6th term</item>
    </string-array>
```



## Screenshots:

![alt tag](https://github.com/DeLaSalleUniversity-Manila/courseadviserapp-ToastyKrabstix/blob/master/device-2015-10-04-201511.png)

![alt tag](https://github.com/DeLaSalleUniversity-Manila/courseadviserapp-ToastyKrabstix/blob/master/device-2015-10-04-201537.png)

