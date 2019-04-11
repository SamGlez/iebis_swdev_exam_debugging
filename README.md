# Welcome to Email Changer!

Hi! This is the magical app that will change your email by some fun alternatives, while getting rid of those evil dots. 

## Bug 1

First of all, the SW was not changing the dots by slashes. This is because the dot in regular expressions means match everything, thus everything being a space.    

    String formattedEmailAddress = emailAddress.replaceAll(".", "/");

In order to solve it, we need two backslashes before the dot, one to escape the slash so it gets through, and the other to escape the dot so it becomes literal.

    String formattedEmailAddress = emailAddress.replaceAll("\\.", "/");

## Bug 2

    switch (random.nextInt(2)){
     case 0:  
            word = new StringBuffer('Y');  
     case 1:  
            word = new StringBuffer('F');  
     case 2:  
            word = new StringBuffer('T');  
    }

This function in the code was limiting the possible random INTs to a bound of 2, which meant that it only could output 0 or 1 as inputs for the switch. 

    switch (random.nextInt(3)) {  
        case 0:  
            word = new StringBuffer('Y');  
     case 1:  
            word = new StringBuffer('F');  
     case 2:  
            word = new StringBuffer('T');  
    }

Changing it to a bound of 3 will finally allow the program to run over all the possible switch options, including 0, 1 and 2. Finally "T" will be a meaninful part of this World. 

## Bug 3 

     word = new StringBuffer('Y');
     
In Java, we use single quotes for literal char s and double quotes for literal String s. StringBuffer uses Strings so therefore chars are not accepted as parameters when creating one. The way to solve this is initializing the StringBuffer with double quotes. 

    word = new StringBuffer("Y");

## Bug 4
Initially, the Switch function missed the breaks in order to jump out of the Switch function after one of the options was entered. So it entered every single one and therefore kept only the last one. 

    switch (random.nextInt(3)) {  
            case 0:  
                word = new StringBuffer('Y');  
         case 1:  
                word = new StringBuffer('F');  
         case 2:  
                word = new StringBuffer('T');  
        }

Introducing the breaks after each option it goes out to complete the rest of the code. The magic is well done now. 

    switch (random.nextInt(3)) {  
        case 0:  
            word = new StringBuffer("Y");  
     break; case 1:  
            word = new StringBuffer("F");  
     break; case 2:  
            word = new StringBuffer("T");  
     break;}


# Ciao. Grazie mille. 

Magic by: Samuel González
