# Ухаалаг авто зогсоолын системийн Use Case диаграмм

```mermaid
flowchart TB
    %% Actors
    Actor1(["Жолооч"])
    Actor2(["Админ"])
    Actor3(["Аюулгүй\nбайдал\nажилтан"])
    
    %% Use cases - бүх нэрсийг зурагт байгаа нэрээр солив
    UC1([" зогсоол хайх "])
    UC2([" зогсоол захиалах "])
    UC3([" зогсоолд орох "])
    UC4([" зогсоолоос гарах "])
    UC5([" төлбөр төлөх "])
    UC6([" санал гомдол илгээх "])
    
    UC7([" зогсоолын\nмэдээлэл\nшинэчлэх "])
    UC8([" төлбөр хэмжээ\nтохируулах "])
    UC9([" систем хянах "])
    UC10([" хэрэглэгчийн\nмэдээлэл хянах "])
    
    UC11([" камер хянах "])
    UC12([" осол аюул\nмэдээлэх "])
    
    UC13([" төлбөрийн систем "])
    
    %% Relationships - Жолооч
    Actor1 --- UC1
    Actor1 --- UC2
    Actor1 --- UC3
    Actor1 --- UC4
    Actor1 --- UC5
    Actor1 --- UC6
    
    %% Relationships - Админ
    Actor2 --- UC7
    Actor2 --- UC8
    Actor2 --- UC9
    Actor2 --- UC10
    
    %% Relationships - Аюулгүй байдал ажилтан
    Actor3 --- UC11
    Actor3 --- UC12
    
    %% Use case хоорондын холбоо (extend, include)
    UC2 -.-> |include| UC1
    UC3 -.-> |include| UC2
    UC5 -.-> |include| UC13
    UC4 -.-> |include| UC5
    
    UC6 -.-> |extend| UC3
    UC6 -.-> |extend| UC4
    
    UC7 -.-> |include| UC9
    UC8 -.-> |include| UC7
    UC10 -.-> |include| UC9
    
    UC12 -.-> |extend| UC11
    
    UC9 -.-> |extend| UC11
