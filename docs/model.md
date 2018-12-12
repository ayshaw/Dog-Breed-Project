Explored Models
=================
We explored various neural network modifications for this dog breed classifcation project. 


CNN 
--------
A CNN or Convolutional Neural Network is a type of deep learning that is commonly used for visual imagery analyzation , ideal for our dog breed classification project. This is because CNN add convolution layers that use learnable filters to find specific patterns or features from the original image. The filters are smaller but with the same number of dimensions for the image and same depth.  For example, an image is usually read as a matrix of three dimensions, and the depth of three which takes into account the 'color' channels (rbg). If we have an image of size *NXN* the read matrix by the neural network has a matrix of size *NXNX3*. This would mean that a filter from a convolution layer is a matrix of size *MXMX3* where *M < N*. Different filters detect different features in each image by sliding through all the spatial locations in the input image and creating a set of activation/feature maps as the output that goes into the next layer in the CNN. 

The CNN model that we used for our project had the following layers: 


From this model we were able to get the the following results: 


ResNet50
----------
For this project we specifically looked at ResNET (Residual Neural Network) for our CNN model. ResNETs are a type of deep residual learning architecture commonly used for image recognition that facilitates the training of deeper networks. We used ResNET50 found Keras, the open-source neural network library. This ResNET follows the architechture by He et al. (2015) found [here](https://arxiv.org/abs/1512.03385)


Description of ResNET model: 


From this model we were able to get the the following results:



The table below shows the models used for this project and the results on the train and test sets. 

**Model Description**       **Train Set Accuracy**       **Test Set Accuracy **
---------------------       ----------------------       ----------------------




Reference:
He, K., Zhang, X., Ren, S. and Sun, J., 2016. Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).







Paragraphs are separated by a blank line.

2nd paragraph. *Italic*, **bold**, and `monospace`. Itemized lists
look like:

  * this one
  * that one
  * the other one

Note that --- not considering the asterisk --- the actual text
content starts at 4-columns in.

> Block quotes are
> written like so.
>
> They can span multiple paragraphs,
> if you like.

Use 3 dashes for an em-dash. Use 2 dashes for ranges (ex., "it's all
in chapters 12--14"). Three dots ... will be converted to an ellipsis.
Unicode is supported. ☺



An h2 header
------------

Here's a numbered list:

 1. first item
 2. second item
 3. third item

Note again how the actual text starts at 4 columns in (4 characters
from the left side). Here's a code sample:

    # Let me re-iterate ...
    for i in 1 .. 10 { do-something(i) }

As you probably guessed, indented 4 spaces. By the way, instead of
indenting the block, you can use delimited blocks, if you like:

~~
define foobar() {
    print "Welcome to flavor country!";
}
~~

(which makes copying & pasting easier). You can optionally mark the
delimited block for Pandoc to syntax highlight it:

~~python
import time
# Quick, count to ten!
for i in range(10):
    # (but not *too* quick)
    time.sleep(0.5)
    print i
~~



### An h3 header ###

Now a nested list:

 1. First, get these ingredients:

      * carrots
      * celery
      * lentils

 2. Boil some water.

 3. Dump everything in the pot and follow
    this algorithm:

        find wooden spoon
        uncover pot
        stir
        cover pot
        balance wooden spoon precariously on pot handle
        wait 10 minutes
        goto first step (or shut off burner when done)

    Do not bump wooden spoon or it will fall.

Notice again how text always lines up on 4-space indents (including
that last line which continues item 3 above).

Here's a link to [a website](http://foo.bar), to a [local
doc](local-doc.html), and to a [section heading in the current
doc](#an-h2-header). Here's a footnote [^1].

[^1]: Footnote text goes here.

Tables can look like this:

size  material      color
----  ------------  ------------
9     leather       brown
10    hemp canvas   natural
11    glass         transparent

Table: Shoes, their sizes, and what they're made of

(The above is the caption for the table.) Pandoc also supports
multi-line tables:

--------  -----------------------
keyword   text
--------  -----------------------
red       Sunsets, apples, and
          other red or reddish
          things.

green     Leaves, grass, frogs
          and other things it's
          not easy being.
--------  -----------------------

A horizontal rule follows.

***

Here's a definition list:

apples
  : Good for making applesauce.
oranges
  : Citrus!
tomatoes
  : There's no "e" in tomatoe.

Again, text is indented 4 spaces. (Put a blank line between each
term/definition pair to spread things out more.)

Here's a "line block":

| Line one
|   Line too
| Line tree

and images can be specified like so:

![example image](example-image.jpg "An exemplary image")

Inline math equations go in like so: $\omega = d\phi / dt$. Display
math should get its own line and be put in in double-dollarsigns:

$$I = \int \rho R^{2} dV$$

And note that you can backslash-escape any punctuation characters
which you wish to be displayed literally, ex.: \`foo\`, \*bar\*, etc.
