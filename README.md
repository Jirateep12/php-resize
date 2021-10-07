# php-resize

```
<?php
// --------
// 1 Resize In Parameter url
// --------


// The file
$filename = "";

// Set a maximum height and width
$width = 5;
$height;

// Content type
header('Content-Type: image/webp');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);

$height = round(($height_orig / $width_orig) * $width);

// Resample
$image_p = imagecreatetruecolor($_GET['width'], $_GET['height']);
$image = imagecreatefromwebp($_GET['image']);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $_GET['width'], $_GET['height'], $width_orig, $height_orig);

// Output
imagewebp($image_p, null, $_GET['quality']);


// --------
// 2 Resize In file
// --------


// The file
$filename = "";

// Set a maximum height and width
$width = 5;
$height;

// Content type
header('Content-Type: image/webp');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);

$height = round(($height_orig / $width_orig) * $width);

// Resample
$image_p = imagecreatetruecolor($width, $height);
$image = imagecreatefromwebp($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $width, $height, $width_orig, $height_orig);

// Output
imagewebp($image_p, null, 100);


// --------
// 3 Resize In file ratio Height 16:9
// --------


// The file
$filename = "";

// Set a maximum height and width
$width = 5;
$height;

// Content type
header('Content-Type: image/webp');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);

$height = round(($height_orig / $width_orig) * $width);

// Resample
$image_p = imagecreatetruecolor($width, $height);
$image = imagecreatefromwebp($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $width, $height, $width_orig, $height_orig);

// Output
imagewebp($image_p, null, 100);


// --------
// 4 Resize In file ratio Width 16:9
// --------


// The file
$filename = "";

// Set a maximum height and width
$width;
$height = 5;

// Content type
header('Content-Type: image/webp');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);

$width = round(($width_orig / $height_orig) * $height);

// Resample
$image_p = imagecreatetruecolor($width, $height);
$image = imagecreatefromwebp($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $width, $height, $width_orig, $height_orig);

// Output
imagewebp($image_p, null, 100);
?>
```
