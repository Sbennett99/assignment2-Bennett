# Seth Bennett
### My Favorite location: 37.2431° N, 115.7930° W
There are so many things that I like about this location, though the **heat** is not one of them. I'd love to share more but all other details are **classified**.

---
### Directions 
1. Leave Maryville north on HWY 136
2. After arriving in Rockport go north on Interstate 29
3. Get off I29 at exit 10 in Iowa and continue west on IA-2
4. After reaching Lincoln Nebraska continue on US-77 North for a short period before getting off onto Interstate 80 West
5. Shortly after passing by Big Springs Nebraska exit onto Interstate 76 West
6. After arriving in Denver Colorado continue onto Interstate 70 West
7. After reaching Sulphurdale Utah continue onto Interstate 15 South
8. Take exit 59 and continue onto UT-56 West
9. Road changes name to NV-319 West upon entering Nevada
10. Upon arrival at US-93, continue South
11. Exit US-93 onto NV-318 N 
    * then keep left onto NV-375 N
12. Stop in Rachel get ready for a hike
    * Hike 25 miles South 
    * Continue Hiking 4 - 5 miles west until you reach your destination

###### A Few Items to Bring
* Hiking equipment
* Lots of water
* A Phone to call your lawyer when you get there, if they let you call them


[More About Me](AboutMe.md)

---

### Recomendations

We all have our favorite meals, whether it is a desert of main course may even vary. Furthermore, with those meals there is always one important addition, the drink. Below is a table showing a few of my fa vorite foods and drinks, as well as their average price and where to get them.

| Food/Drink item | Location | Price |
| --------------- | -------- | ----- |
| Angel Food Cake | Hyvee    | $7.00 |
| Spaghetti       | Olive Garden | $13.00 |
| Pepsi           | Caseys   | $2.00 |
| Breakfast Pizza | Caseys   | $2.00 |

---
### Quotes

> Not all those who wander are lost
> *- J.R.R. Tolkien*

> Time is the most valuable asset you don't own. You may not realize it yet, but how you use or don't use your time is going to be the best indication of where your future is going to take you.
> *- Mark Cuban*

---
### Algorithm

> ***Klee's Algorithm***
> 
> 1) Put all the coordinates of all the segments in an auxiliary array points[]. 
> 2) Sort it on the value of the coordinates. 
> 3) An additional condition for sorting – if there are equal coordinates, insert the one which is the left coordinate of any segment instead of a right one. 
> 4) Now go through the entire array, with the counter “count” of overlapping segments. 
> 5) If the count is greater than zero, then the result is added to the difference between the points[i] – points[i-1]. 
> 6) If the current element belongs to the left end, we increase “count”, otherwise reduce it.
> [Source: Klee's Algorithm](https://www.geeksforgeeks.org/klees-algorithm-length-union-segments-line/)

```Java
int length_union(const vector<pair<int, int>> &a) {
    int n = a.size();
    vector<pair<int, bool>> x(n*2);
    for (int i = 0; i < n; i++) {
        x[i*2] = {a[i].first, false};
        x[i*2+1] = {a[i].second, true};
    }

    sort(x.begin(), x.end());

    int result = 0;
    int c = 0;
    for (int i = 0; i < n * 2; i++) {
        if (i > 0 && x[i].first > x[i-1].first && c > 0)
            result += x[i].first - x[i-1].first;
        if (x[i].second)
            c--;
        else
            c++;
    }
    return result;
}
```
[Code Source](https://cp-algorithms.com/geometry/length-of-segments-union.html)