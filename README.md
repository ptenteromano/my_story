Phil Tenteromano
----------------
<a href="https://github.com/ptenteromano/" target="_blank">github</a> |
<a href="https://www.linkedin.com/in/tenteromano/" target="_blank">linkedin</a> |
<a href="https://twitter.com/ptenteromano/" target="_blank">twitter</a>

Welcome to my Github pages static website where I'll try to keep things short and sweet.
My goal for this repository/website is to have a place to talk about where I am today, where I came from, and how I got here.

I hope you enjoy my story.

>"The function of education is to teach one to think intensively and to think critically. Intelligence plus character - that is the goal of true education." -Martin Luther King, Jr.

### The U.S. Army

Before joining the military, I had done two semesters in college and just didn't know what I wanted to do. After some thought and reflection, I decided to join the Army in 2012 as a way of serving my country and myself. I served four years on Active duty from _2012 - May 2016_. I can honestly say my time in the military was one of the best experiences of my life. I am forever grateful for the friendships I made and the places I've been to and the skills I've learned.

Some of the places I've been to in my four years:
* Virginia, South Carolina for Training
* Natick, MA for 6 months temporary Duty
* Dongducheon, South Korea as my first permanent Duty Station
* Fort Bliss, Texas in El Paso
* Al-Asad, Iraq with my Texas unit
* Camp Behring, Kuwait

I loved the travelling, but as amazing as it was, I had no ambition to stay in forever. I grew as a person and wanted to challenge myself intellectually. I always knew about the incredible benefit of the GI Bill, and I started building out a five-year plan for myself during my final year in the military. Around the last year of the army I spoke with family and friends about potential options for my future; my brother introduced me to code and software development back in 2015. After researching into it more, it became clear to me that my interest wasn't forced - I was thoroughly enjoying the topics contained in computer science. 

### Transitioning and Gaining Traction

The end of my contract couldn't come at a more opportune time. I was applying to colleges in NYC while finishing the last few months in the Army in El Paso, Texas. I grew up in New York, born in Brooklyn and raised in the suburbs, I desperately wanted to drive for success - my goal was work and live in Manhattan.

Not only were my family and friends doing well in and around NYC, but the GI Bill had a great stipend for the area, too. I was so relieved and excited when I got into Fordham University under there Yellow Ribbon Program. I immediately started meeting other Veterans and being apart of their FVA (Fordham Veteran Assocation). 

After hammering out the details, I was separated from the Army on May 19th, 2016 - less than two weeks later, on May 31st, 2016, I was in a NYC classroom taking Structures of Computer Science CISC 1400 at Fordham University.

### Continuing School and Building Skills

It's been two years now, at first I thought college would be the only thing I need to succeed. I was getting great grades, always early to class, and having an overall greater appreciation for where I am and where I want to go. Except computer science demands a little extra. 

In January of 2017 I realized I need to be doing more on my own time in order to really become a confident, knowledgable 'Software Engineer'. That's when I started my in-parallel self-taught studies while taking upper level college courses. Since then I have taken courses on Udemy, Coursera, Zenva Acadamy, read countless articles, built github repositories in numerous languages, and more. 

This Summer (2018), I continued to take Summer courses are Fordham while also being apart of a small Brooklyn startup's software intern team. The company, Everlasting Wardrobe, supplies rental clothing to their clients for kids up to age 12. I was apart of their backend engineering team using the Ruby on Rails framework for their web application.

I am also in the middle of building a full-stack website for my buddies' podcast *_Throat Culture_*. They are on most of the platforms for podcasting and I've decided to be apart of it by making a Blog site which they can use to discuss topics with their users. It is in it's final stages, as I have done this myself, but I also plan on building a merchandise store for them on the site also. I can link that site when it finally goes live.

Currently I am heading into the Fall 2018 semester as my last semester. December of 2018 I will have my Bachelor's of Science in Computer Science from Fordham. 

But school won't end for me there, I've done the math and planned it all out - my GI Bill continues and so I've applied and been accepted to Fordham's Graduate program for M.S. in *Data Analytics*. 

### What's Next

I plan on having my M.S. in Data Analytics by December of 2019. With my veteran, collegiate, professional, and self-taught experience, I hope to be apart of a company that has great ideas and wants to build great software. When I graduate with my Master's, I would like to work as a Software Engineer for a few years, learning and growing my skillset.

My ultimate goal, however, is to specialize in Data Science - hence, the M.S. specializiation. I believe having the necessary experience in Software Engineering can help me to become a better Data Scientist down the road.

-----

#### Preferred Tech Stack and Languages I've used:

I started with C++ when I first started Fordham more than 2 years ago. I also have used:

* Python - Wrote a webscraper with Python, I love this language. Big in data science!
* Ruby / Rails - Used at my Internship and my own personal projects.
* C++ - Most of my undergrad coursework is in C++, what a great language!
* Java - Created some programs with a GUI interface.
* JavaScript - I am currently working on a React and Node.js Course to deepend my JS skills
* HTML / CSS - Where would any good programmer be without these two?
* Always learning!


#### JavaScript Algorithm!

I practice algorithms during the rare times I'm not studying for school, building projects, or refactoring code.
Here is an example JS algorithm that outputs the max number in each window as it slides across an array.
For example, an array of [10, 8, 34, 20, 5] with a window size of 2 will output:
* [10, 34, 34, 20], as the window slides from left to right, store the max int into results array.

```javascript
// Philip Tenteromano
// Sliding Window Algorithm
// O(n) Linear runtime 
// O(w) memory complexity (w == window size)

// window size in array, store max in the window as it slides to end

let max_sliding_window = function(arr, window_size) {
  if (window_size > arr.length) {
    return "Window exceeds List Size";
  }

  let result = [];
  let list_ = [];

  // finding max of first window in array
  // storing the INDEX of the max -- it stays at list_[0]
  for (let i = 0; i < window_size; i++) {
    // compares current array index with last elements in window list
    // removes if current is larger
    while (list_.length > 0 && arr[i] >= arr[list_[list_.length - 1]]) {
      list_.pop();
    }
    list_.push(i);
  }

  result.push(arr[list_[0]]);

  // clear trailing smaller numbers and
  // shift through the rest of the array with the window
  for (let i = window_size; i < arr.length; i++) {
    while (list_.length > 0 && arr[i] >= arr[list_[list_.length - 1]]) {
      list_.pop();
    }

    // (i - window_size) gives the index of 'list_' head!
    if (list_.length > 0 && (list_[0] <= i - window_size)) {
      // shift method is like pop but on the head
      list_.shift();
    }

    list_.push(i);
    // remember list_ only holds the index of the numbers
    result.push(arr[list_[0]]);
  }

  return result;
};


let a = [3, 5, -2, 8, -3, 12];

console.log(max_sliding_window(a, 2));
console.log("-----------------");
console.log(max_sliding_window(a, 3));
console.log("-----------------");
console.log(max_sliding_window(a, 4));
console.log("-----------------");
console.log(max_sliding_window(a, 5));

```

<div style="margin: auto; text-align: center;" markdown="1">
![alt]({{site.url}}{{site.baseurl}}/army.jpg "Army") 
![alt]({{site.url}}{{site.baseurl}}/fordham_university.jpg "Fordham")
</div>

I plan on putting my React skills to the test to revamp this site using React. Coming Soon.

