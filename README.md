class Person {
  name;

  constructor(name) {
    this.name = name;
  }

  introduceSelf() {
    console.log(`Hi! I'm ${this.name}`);
  }
}
This declares a class called Person, with:

a name property.
a constructor that takes a name parameter that is used to initialize the new object's name property
an introduceSelf() method that can refer to the object's properties using this.

2)UBER PRICE IN JS

class UberPrice {
  constructor() {
    this.interval = null;
    this.prices = [];
    this.pages = 0;
    this.lastTrip = null;
  }

  getNextButton() {
    return $('.btn.pagination__next');
  }

  getLastTrip() {
    return $('#trips-table tbody tr:nth-last-child(2)')
      .children()
      .map((i, e) => e.innerHTML)
      .toArray()
      .join();
  }

  getSum(currency = 'UAH') {
    return this.prices.filter(p => p.indexOf(currency) !== -1)
      .map(p => p.slice(3)).map(parseFloat)
      .reduce((acc, x) => acc + x, 0);
  }

  parse() {
    const currentPrices = $('td.text--right')
      .map((i, e) => e.innerHTML)
      .filter((k,e) => e.indexOf('Canceled') === -1)
      .toArray()
      .map(price => price.match(/[A-Z]{3}.*/g))
      .filter(e => e)
      .map(p => p[0]);

    this.lastTrip = this.getLastTrip();
    this.prices = this.prices.concat(currentPrices);
  }

  nextPage() {
    const page = window.location.href;
    const $button = this.getNextButton();

    $button.click();

    console.log('PAGE: ', page);

    this.interval = setInterval(
      () => {
        if (window.location.href !== page) {
          clearInterval(this.interval);
          setTimeout(() => {
            this.run();
          }, 1000);
        }
      }, 300);
  }

  incrementPages() {
    this.pages += 1;
  }

  run() {
    this.parse();
    this.incrementPages();
    this.nextPage();
  }
}

const p = new UberPrice();

p.run();

3)CLASS-MOVIE

class Movie:
    def __init__(self, title, studio, rating="PG"):
        self.title = title
        self.studio = studio
        self.rating = rating

    @staticmethod
    def getPG(movies):
        pg_movies = [movie for movie in movies if movie.rating == "PG"]
        return pg_movies
casino_royale = Movie(title="Casino Royale", studio="Eon Productions", rating="PG-13")

Explanation:

a) The constructor (__init__ method) takes three parameters (title, studio, and rating). It sets the class properties (self.title, self.studio, and self.rating) to the provided values. The rating parameter has a default value of "PG" if not provided.

b) The default value for the rating parameter in the constructor is set to "PG".

c) The getPG method takes an array of Movie instances and returns a new array containing only those movies with a rating of "PG".

d) Creating an instance of the Movie class with the specified title, studio, and rating.

You can now use the casino_royale instance or create more instances of the Movie class and use the getPG method as needed.

4)
+---------------------+
|      Person         |
+---------------------+
| - name: String      |
| - age: Double       |
+---------------------+
| + setName(name: String): void   |
| + setAge(age: Double): void     |
| + getName(): String             |
| + getAge(): Double              |
+---------------------+

  class Person {
  private name: string;
  private age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  setName(name: string): void {
    this.name = name;
  }

  setAge(age: number): void {
    this.age = age;
  }

  getName(): string {
    return this.name;
  }

  getAge(): number {
    return this.age;
  }
}
n the TypeScript class:

I've used string for the name attribute and number for the age attribute as per your request to use a number for double.
private access modifiers are used to encapsulate the class attributes.
There's a constructor to initialize the object with values for name and age.
Getter and setter methods are provided for accessing and modifying the attributes.
Feel free to adapt this example based on the specific details of your UML diagram or provide additional details if you need a more complex conver
