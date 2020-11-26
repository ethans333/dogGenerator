# Random Dog Generator
Generates random dog info. Info such as their name, breed, age, color.


### Main.java
``` Java
public class Main {
    public static void main(String args []) {
        for (int i = 0; i < 25; i++) {
            Dog dog = new Dog();
            System.out.println(dog.getInfo());
        }
    }
}
```

### Dog.java
``` Java
public class Dog {
    public String[] breeds = {"Golden Retriever", "Black Lab", "Pit Bull"};
    public String[] colors = {"Brown", "Black", "White", "Baige"};

    public String randomName(int nameLength) {
        String[] chars = ("abcdefghijklmnopqrstuvwxyz").split("");
        String[] vowels = ("aeiou").split("");
        String name = "";

        for(int i = 0; i < nameLength; i++){
            if (i > 0 && i < nameLength-1){
                name += vowels[(int)(Math.random() * vowels.length)];
            } else {
                name += chars[(int)(Math.random() * chars.length)];
            }
        }

        return name;
    }

    String name = randomName(3);
    int age = (int)(Math.random() * 14) + 1;
    String breed = breeds[(int)(Math.random() * breeds.length)];
    String color = colors[(int)(Math.random() * colors.length)];

    public String getInfo() {
        return String.format("Name: %s %nAge: %s %nBreed: %s %nColor: %s %n", 
        this.name, this.age, this.breed, this.color);
    }
}

```

I made this project just for fun. An easy exercise to start learning Java. Once I finished the program and ran it
on the sixth time the name generated was 'Koa'. Thats my dogs name. With conditions of the name being a three letter
word, and the middle letter being a random vowel the probability of that happening on my sixth time running it is extremely
low! Specifically there would be **1/563** chance or **.1775%** chance that I'd get the name 'Koa' on my  sixth time running
the generator!
