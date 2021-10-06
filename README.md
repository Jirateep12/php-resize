# php-resize

```
<?php
// --------
// 1 Resize 
// --------


// The file
$filename = $_GET['image'];

// Content type
header('Content-Type: image/webp');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($_GET['image']);
$ratio_orig = $width_orig / $height_orig;

// if ($width / $height > $ratio_orig) {
//   $width = $height * $ratio_orig;
// } else {
//   $height = $width / $ratio_orig;
// }

// Resample
$image_p = imagecreatetruecolor($_GET['width'], $_GET['height']);
$image = imagecreatefromwebp($_GET['image']);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $_GET['width'], $_GET['height'], $width_orig, $height_orig);

// Output
imagewebp($image_p, null, $_GET['quality']);


// --------
// 2 Resize 
// --------


// The file
$filename = $_GET['image'];

// Set a maximum height and width
$width = 5;
$height = 7;

// Content type
header('Content-Type: image/webp');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);
$ratio_orig = $width_orig / $height_orig;

// if ($width / $height > $ratio_orig) {
//   $width = $height * $ratio_orig;
// } else {
//   $height = $width / $ratio_orig;
// }

// Resample
$image_p = imagecreatetruecolor($width, $height);
$image = imagecreatefromwebp($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $width, $height, $width_orig, $height_orig);

// Output
imagewebp($image_p, null, 100);
?>
```
