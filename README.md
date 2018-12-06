# Swipe Refresh Layout - Documentation

# I. Introduction 

Swipe-to-refresh is a widely used function in almost all apps today. By performing a vertical swipe, the user can trigger an instant update on the app. It is a nice fit for for adapter-backed views (For example, ListView and RecyclerView) that require user-requested refreshes, like displaying Facebook notification list.

In Android, this is implemented by the SwipeRefreshLayout widget. The widget detects the vertical swipe, displays whether a progress bar or a circular icon (which will disappear when the update completes), and triggers callback methods in the app. 

# II.Background 

SwipeRefreshLayout is added in version 22.1.0 (Lollipop 5.1) and located in Java.lang.Object --> android.view.View --> android.view.ViewGroup --> android.support.v4.widget.SwipeRefreshLayout

Traditionnally, ListView is the most well-known way to display a collection of views, images, data. However, with the birth of SwipeRefreshLayout, RecyclerView is also created for better view holders and more advanced optimization overall. Together, they bring the best experience possible for users to constantly update the screen with different type of data and data sizes. 

Both views have the same way to apply SwipeRefreshLayout:
1. Initialize a SwipeRefreshLayout and the corresponding View in XML file
2. Get reference for both in the desired Activity.
3. Create a String list of data.
4. Implement the equivalent adapter (ArrayAdapter for ListView, and RecyclerView Adapter for RecyclerView)
5. Implement setOnRefreshListener event on SwipeRefreshLayout. 
6. Display list items and set the adapter in our own method.

# III. Major constructors/methods/attributes

### III.1 Constructors

The constructor is SwipeRefreshLayout, but different parameters are used for different scenarios:

1. SwipeRefreshLayout (Context context): Simple constructor to use when creating a SwipeRefreshLayout from code. Context is an abstract class that is provided by Android System. It permits the user to work with other classes and resources, as well as application-level processes, such as launching activities, managing intents,...

2. SwipeRefreshLayout (Context context, AttributeSet attrs): Constructor that is called when inflating SwipeRefreshLayout from XML. Context class is explained above. AttributeSet presents an effective way of capturing data from compiled XML files, which can be retrieved for a specific XMLPullParser through Xml.asAttributeSet(). However, often you do not want to use AttributeSet directly.

### III.2 Methods/Attributes

There are many methods displayed in the Android Developer Webpage, but these are the required ones to run a basic SwipeRefreshLayout:

1. setOnRefreshListener(OnRefreshListener): This method adds a listener to notify other parts of the code know when the refreshing starts.

2. setRefreshing(boolean): This method determines whether or not the current view show refresh progress. It can be a progress bar or a circular motion. Do not call this when refresh is triggered by a swipe gesture.

 2.1 setRefreshing(false): Is called when a refresh is declared not to be executed. Any visual indication of a refresh will be cancelled.

 2.2 setRefreshing(true): Is called when the activity is allowed to display the refresh animation.

3. isRefreshing(): Checks if the SwipeRefreshWidget is actively showing the update progress. 

Other methods that can be considered, for better UI experience:

4. void setColorSchemeColors (int colors): Set the colors used in progress animation. 

5. setProgressViewOffset (boolean scale, int start, int end): This method is used to adjust the starting and ending position of the refresh indicator. 

# IV. Example Project & Code

The example project and code has been attached to this repository. Only one Java file and XML file is needed, which can be found <a href="https://raw.githubusercontent.com/ngtrangminhduc/SwipeRefreshLayout/master/app/src/main/java/com/example/ducnguyen/swiperefreshlayoutcode/MainActivity.java">here</a> and <a href="https://raw.githubusercontent.com/ngtrangminhduc/SwipeRefreshLayout/master/app/src/main/res/layout/activity_main.xml">here</a>

For a complete demonstration purpose , there's a 15 seconds video named <a href="https://raw.githubusercontent.com/ngtrangminhduc/SwipeRefreshLayout/master/Demonstration.mp4">Demonstration.mp4</a>  

For convenient purposes, here are the demonstrative screenshots:

1. This is the former list:

![alt text](https://github.com/ngtrangminhduc/SwipeRefreshLayout/blob/master/Screenshot_1.png)

2. This is where the SwipeRefreshLayout begins. As soon as I performed a vertical slide, the pink circular icon appeared.

![alt text](https://github.com/ngtrangminhduc/SwipeRefreshLayout/blob/master/Screenshot_2.png)

3. As soon as I released, the circular icon started rotating. After nearly 1 second, the list was updated.

![alt text](https://github.com/ngtrangminhduc/SwipeRefreshLayout/blob/master/Screenshot_3.png)


# V. Reference
https://developer.android.com/reference/android/support/v4/widget/SwipeRefreshLayout
https://abhiandroid.com/materialdesign/pulltorefresh
