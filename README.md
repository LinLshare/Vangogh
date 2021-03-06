# Vangogh
[中文版](https://github.com/LinLshare/Vangogh/blob/master/README-zh.md)
A Simple Image Selector for Android, just do the image-selection job. You can do anything with your view and let Vangogh handle the data.

![ScreenShot1](https://raw.githubusercontent.com/LinLshare/Vangogh/master/screenshot/ss_1.png)
![ScreenShot2](https://raw.githubusercontent.com/LinLshare/Vangogh/master/screenshot/ss_2.png)
![ScreenShot3](https://raw.githubusercontent.com/LinLshare/Vangogh/master/screenshot/ss_3.png)
![ScreenShot4](https://raw.githubusercontent.com/LinLshare/Vangogh/master/screenshot/ss_4.png)

## Don't do
1. no permission request
2. no view or activity
3. no adapter
4. no image compress

## Do
1. image filter by name, path, size type and count
2. select image and deselect image

## Usage

1. Init first

```java
Filter filter = new Filter.Builder().mimType(MimeType.JPEG)
                                    .nameRegex(".*wx_camera.*")
                                    .limitCount(3)
                                    .pathContain("/tencent/MicroMsg/WeiXin")
                                    .build();
Vangogh.create(filter).init(this);
```

2. Get all album and image to show

```java
List<Album> alba = Vangogh.albumList();
List<Image> imageList = Vangogh.imageList(album);
```

3. Toggle select when Image Item click

```java
Vangogh.getInstance().toggleSelect(album, image);
```

4. Get selected image when OK

```java
Map<Album, List<Image>> albumListMap = Vangogh.selectedImageMap();
```

5. Clear selection

```java
Vangogh.selectNone();
```

## Fuli
In Sample Project, I provide the extra activity and adapter implementation. 

## Thanks
1. [darsh2/MultipleImageSelect](https://github.com/darsh2/MultipleImageSelect) 
2. [zhihu/Matisse](https://github.com/zhihu/Matisse)