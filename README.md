# Motion Tab Bar v2, with null-safety support

A beautiful animated widget for your Flutter apps

**Preview:**

### v0.2.x Screenshot
![0.2.1 Screenshot](https://github.com/kimmanwky/Motion-Tab-Bar/blob/master/screenshot2.png?raw=true)  

### v0.1.x Preview (animatation)
![MotionTabBar Gif](https://github.com/therezacuet/Motion-Tab-Bar/blob/master/motiontabbar.gif?raw=true)

<br>

## Getting Started

Add the plugin:

```yaml
dependencies:~
  motion_tab_bar: ^0.2.1
```

## Basic Usage

Adding the widget

```dart
   MotionTabController _tabController;
  @override
  void initState() {
    super.initState();
    _tabController = new MotionTabController(initialIndex:1,vsync: this);
  }

  @override
  void dispose() {
    super.dispose();
    _tabController.dispose();
  }

  bottomNavigationBar: MotionTabBar(
    initialSelectedTab: "Home",
    labels: const ["Dashboard", "Home", "Profile", "Settings"],
    icons: const [Icons.dashboard, Icons.home, Icons.people_alt, Icons.settings],

    // optional badges, length must be same with labels
    badges: [
      // Default Motion Badge Widget
      const MotionBadgeWidget(
        text: '99+',
        textColor: Colors.white, // optional, default to Colors.white
        color: Colors.red, // optional, default to Colors.red
        size: 18, // optional, default to 18
      ),

      // custom badge Widget
      Container(
        color: Colors.black,
        padding: const EdgeInsets.all(2),
        child: const Text(
          '48',
          style: TextStyle(
            fontSize: 14,
            color: Colors.white,
          ),
        ),
      ),

      // allow null
      null,

      // Default Motion Badge Widget with indicator only
      const MotionBadgeWidget(
        isIndicator: true,
        color: Colors.red, // optional, default to Colors.red
        size: 5, // optional, default to 5,
      ),
    ],
    tabSize: 50,
    tabBarHeight: 55,
    textStyle: const TextStyle(
      fontSize: 12,
      color: Colors.black,
      fontWeight: FontWeight.w500,
    ),
    tabIconColor: Colors.blue[600],
    tabIconSize: 28.0,
    tabIconSelectedSize: 26.0,
    tabSelectedColor: Colors.blue[900],
    tabIconSelectedColor: Colors.white,
    tabBarColor: const Color(0xFFAFAFAF),
    onTabItemSelected: (int value) {
      // ignore: avoid_print
      print(value);
      setState(() {
        _tabController!.index = value;
      });
    },
  )

```