Hi, I'm Carlos Vasquez, and I'm a student at the George Westinghouse Highschool and also at the STEAM Center, Full-Stack Development Pathway. Something about me is that I like studying technology as much as I can and want to learn more about it. I participate in a lot of programs when they are available like internships and participate in FIRST Robotics Competition as the current student Team Captain of Team 354 and also one of the managers for the Westinghouse JV Basketball team.

![One of my friend's photo](/assets/torres.png)

<ul>
    {% for post in sites.posts %}
        <li>
            <a href="/blog{{ post.url }}">{{ post.title}}</a>
        </li>
    {% endfor %}
</ul>