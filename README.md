<?php

// Include the library
require_once 'vendor/autoload.php';

use Endroid\QrCode\QrCode;

// Set the data that you want to encode
$data = 'This is the data that I want to encode in the QR code';

// Create a new QR code object
$qrCode = new QrCode($data);

// Set the size of the QR code (in pixels)
$qrCode->setSize(300);

// Set the background color of the QR code
$qrCode->setBackgroundColor(['r' => 255, 'g' => 255, 'b' => 255, 'a' => 0]);

// Set the foreground color of the QR code
$qrCode->setForegroundColor(['r' => 0, 'g' => 0, 'b' => 0, 'a' => 0]);

// Set the label (content at the center of the QR code)
$qrCode->setLabel('Scan this QR code');

// Set the label font size
$qrCode->setLabelFontSize(16);

// Output the QR code as a PNG image
header('Content-Type: '.$qrCode->getContentType());
echo $qrCode->writeString();
