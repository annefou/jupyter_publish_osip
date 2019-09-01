---
title: 'Introduction'
prev_page:
  url: 
  title: ''
next_page:
  url: /jupyter_publish-1.html
  title: 'Jupyter Publish-1'
layout: episode

teaching: 20

exercises: 0

questions:

  - "How can we ease writing out research results along the way?"

  - "How can we openly share articles, code, and data in all phases of the research process?"

objectives:

  - "Understand that the research lifecycle is not an iterative process"

  - "Understand how to streamline your research work by using every opportunities to share and make publicly available all phases of your research process"

keypoints:

  - "Open science is simply science."

comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

One important aspect to embrace Open Science is to base your scientific process on cooperative work and use many different ways 
for diffusing knowledge to be as inclusive as possible.  
Achieving openness requires an open approach at all stages of the research process and requires you to identify the key actors 
i.e. your target audience. As this may evolve, it is important to choose tools that can facilitate the diffusion of your research results.  

That is exactly what we are addressing in this workshop.

Ideally, Open Science is simply Science.

> ## Discussion points
>
> In practice, what are the obstacles to Open Science?
>
{: .task}


> ## Widgets for interactive data fitting
>
> Widgets are fun, but they can also be useful. Here's an example showing how you can fit noisy data interactively.
>
> 1. Execute the cell below. It fits a 5th order polynomial to a gaussian function with some random noise
> 2. Use the `@interact` decorator together with the function `fit`,
>    such that you can visualize fits with polynomial orders `n`
>    ranging from, say, 3 to 30:
>
> ```python
> import matplotlib.pyplot as plt
> # gaussian function
> def gauss(x,param):
>     [a,b,c] = param
>     return a*np.exp(-b*(x-c)**2)
>
> # gaussian array y in interval -5<x-5
> nx = 100
> x = np.linspace(-5.,5.,nx)
> p = [2.0,0.5,1.5] # some parameters
> y = gauss(x,p)
>
> # add some noise
> noise = np.random.normal(0,0.2,nx)
> y += noise
>
> # we fit a 5th order polynomial to it
>
> def fit(n):
>     pfit = np.polyfit(x,y,n)
>     yfit = np.polyval(pfit,x)
>     plt.plot(x,y,"r",label="Data")
>     plt.plot(x,yfit,"b",label="Fit")
>     plt.legend()
>     plt.ylim(-0.5,2.5)
>     plt.show()
>
> # call function fit
> # these lines are unnecessary when you use the interact widget
> n=5
> fit(n)
> ```
>
> > ## Solution
> >
> > ```python
> > import numpy as np
> > from ipywidgets import interact
> > import matplotlib.pyplot as plt
> > %matplotlib inline
> >
> > # gaussian function
> > def gauss(x,param):
> >     [a,b,c] = param
> >     return a*np.exp(-b*(x-c)**2)
> >
> > # gaussian array y in interval -5<x-5
> > nx = 100
> > x = np.linspace(-5.,5.,nx)
> > p = [2.0,0.5,1.5] # some parameters
> > y = gauss(x,p)
> >
> > # add some noise
> > noise = np.random.normal(0,0.2,nx)
> > y += noise
> >
> > @interact
> > def fit(n=(3,30)):
> >     pfit = np.polyfit(x,y,n)
> >     yfit = np.polyval(pfit,x)
> >     plt.plot(x,y,"r",label="Data")
> >     plt.plot(x,yfit,"b",label="Fit")
> >     plt.legend()
> >     plt.ylim(-0.5,2.5)
> >     plt.show()
> > ```
> {: .solution}
{: .challenge}

