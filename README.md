# C-
#include <iostream>

#include <fstream>
#include<vector>

 

using namespace std;

const int maxCourseAmt = 99;

 

struct Course

{

    string Course = "";

    int Credit = 0;

int Score = 0;

int Grade = 0;

};

 

struct Student

{

    int ID = 0;

    string Name = "";

    vector<Course>Courses;

};

 

int isInArray(Student arr[], int target)

{

    int i = 0;

    while (arr[i].ID != 0)

    {

        if (arr[i].ID == target)
            return i;
        i++;
    }

    return -1;
    


}
 

int main()

{

    fstream inputFile;

    string  fileName = "StudentRecords.txt";

    string token;

    Student arrStu[9];

 

    inputFile.open(fileName, ios::in);

    if (inputFile.is_open())

    {

 

        int index = 0;

        int ID;

        string Name;

        string CourseName;

        int Credit;

        int Score;
        
        int G;
        double GPA;

        while(!inputFile.eof())

        {

            inputFile >> ID >> Name >> CourseName >> Credit >> Score;

 

            int ii = isInArray(arrStu, ID);

            if (ii == -1) // The student record does not exist

            {

                arrStu[index].ID  = ID;

                arrStu[index].Name = Name;
                
                Course c;

                arrStu[index].Courses.push_back(c);

                arrStu[index].Courses[0].Course=CourseName;
                arrStu[index].Courses[0].Credit=Credit;
                 arrStu[index].Courses[0].Score=Score;
                

                index++;

            }

            else /// The student exists

            {
                      Course c;
                c.Course=CourseName;
                c.Credit=Credit;
                c.Score=Score;

                arrStu[index].Courses.push_back(c);

           
                
               

               
                

                /// Add course and score to the existing student record

            }
            
       
            
            
            /*for(int i=0;i<index;i++)
            {
             cout<<arrStu[i].ID;
             for(int j=0;j<arrStu[i].arrCourse.size();j++)
             {
             cout<<arrStu[i].arrCourse[j].Course<<endl;
             cout<<arrStu[i].arrCourse[j].Credit<<endl;
             }
             
             if (arrStu[i].arrCourse[j].Score>0||arrStu[i].arrCourse[j].Score<60)
             {G=0.0;}
              if (arrStu[i].arrCourse[j].Score>60||arrStu[i].arrCourse[j].Score<69)
              {G=1.0;}
               if (arrStu[i].arrCourse[j].Score>69||arrStu[i].arrCourse[j].Score<79)
              {G=2.0;}
              if (arrStu[i].arrCourse[j].Score>79||arrStu[i].arrCourse[j].Score<89)
              {G=3.0;}
               if (arrStu[i].arrCourse[j].Score>89||arrStu[i].arrCourse[j].Score<99)
              {G=4.0;}
              
              GP=arrStu[i].arrCourse[j].Credit*G
              PA= + arrStu[i].arrCourse[j].Credit
              GPA= (+ GP)/PA
              
              */
             
             
        }
        
        

        inputFile.close();

    }

    else

        cout << "File cannot be opened.";
        
        
        

    return 0;

}
