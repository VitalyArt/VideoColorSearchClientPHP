# VideoColor PHP Search Client

This library is designed to find information about a movie and get the frame position using a screenshot from a video.
The call is made to the site https://www.videocolor.aapsoftware.ru.
The number of free calls is limited. To remove restrictions, contact the site owner.

Usage example

//------------------------------------------------------
use AapSoftware\VideoColor\SearchClient;

...

$img = imagecreatefromjpeg($fname);
$search = new AapSoftware\VideoColor\SearchClient();
$obj = $search->get($img);
imagedestroy($img);

if ($obj === null) {
    echo "Server not connected!\n";
    return;
} elseif (!$obj->result) {
	echo "Not found\n";
} else {
	echo "Title:\t" . $obj->title . "\n";
	echo "Frame:\t" . $obj->frame."\n";
	echo "Position:\t" . $obj->position . "\n";
	echo "Duration:\t" . $obj->duration . "\n";
	echo "Producer:\t".$obj->producer."\n";
	echo "Country:\t".$obj->country."\n";
	echo "Creation year:\t".$obj->creation_year."\n";
	echo "Genre:\t".$obj->genre."\n";
	echo "Actors:\t".$obj->actors."\n";
	echo "IMDB:\t".$obj->imdb."\n";
	echo "Kinopoisk:\t".$obj->kinopoisk."\n";
	echo "Description:\t".$obj->description."\n";
}
//------------------------------------------------------

