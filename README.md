# Swipe Refresh Layout

### I. Introduction && History 

Swipe-to-refresh is a widely used function in almost all apps today. By performing a vertical swipe, the user can trigger an instant update on the app. It is a nice fit for for adapter-backed views (For example, ListView and RecyclerView) that require user-requested refreshes, like displaying Facebook notification list.

In Android, this is implemented by the SwipeRefreshLayout widget. The widget detects the vertical swipe, displays whether a progress bar or a circular icon (which will disappear when the update completes), and triggers callback methods in the app. 

### II.Background

SwipeRefreshLayout is added in version 22.1.0 (Lollipop 5.1) and located in Java.lang.Object --> android.view.View --> android.view.ViewGroup --> android.support.v4.widget.SwipeRefreshLayout

Traditionnally, ListView is the most well-known way to display a collection of views, images, data. However, with the birth of SwipeRefreshLayout, RecyclerView is also created for better view holders and more advanced optimization overall. Together, they bring the best experience possible for users to constantly update the screen with different type of data and data sizes. 

Both views have the same way to 

### III. Major methods/attributes

There are many methods displayed in the Android Developer Webpage, but these are the required ones to run a basic SwipeRefreshLayout:

1. setOnRefreshListener(OnRefreshListener): This method adds a listener to notify other parts of the code know when the refreshing starts.

2. setRefreshing(boolean): This method determines whether or not the current view show refresh progress. It can be a progress bar or a circular motion. Do not call this when refresh is triggered by a swipe gesture.

2.1 setRefreshing(false): Is called when a refresh is declared not to be executed. Any visual indication of a refresh will be cancelled.

2.2 setRefreshing(true): Is called when the activity is allowed to display the refresh animation.

3. isRefreshing(): Checks if the SwipeRefreshWidget is actively showing the update progress. 

Other methods that can be considered, for better UI experience:

4. void setColorSchemeColors (int colors): Set the colors used in progress animation. 

5. setProgressViewOffset (boolean scale, int start, int end): This method is used to adjust the starting and ending position of the refresh indicator. 

### IV. Example Project & Code

### V. Reference

