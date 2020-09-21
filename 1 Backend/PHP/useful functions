# Useful php functions

## clear encoded strings

    function clearEncodedStrings($string){
    			$tempstr = Array("Ä" => "AE", "Ö" => "OE", "Ü" => "UE", "ä" => "ae", "ö" => "oe", "ü" => "ue");
    			$string = strtr($string, $tempstr);
    			$string = str_replace(' ', '-', $string);
    			$clean = strtolower($string);
    			return $clean;
    		};

##  remove auto p

    //Remove WPAUTOP from ACF TinyMCE Editor
    	function acf_wysiwyg_remove_wpautop() {
    	    remove_filter('acf_the_content', 'wpautop' );
    	}
    	add_action('acf/init', 'acf_wysiwyg_remove_wpautop');


    // only in certain cases
    	function removeParagraph($string){
    			$string = str_replace(array("<p>", "</p>"), '', $string);
    			return $string;
    		}



### debug in the console

add this file to function.php


	function console_log( $data ){
	echo '<script>';
	echo 'console.log('. json_encode( $data ) .')';
	echo '</script>';
	}


### cut paragraph and add ellipsis

	function ellipseParagraph( $string ){
				$rawCut = substr($string, 0, 50);
				$lastSpacePos = strrpos($rawCut, " ");
				$cleanCut = $rawCut = substr($rawCut, 0, $lastSpacePos);
				return $cleanCut . "…";
			}
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1OTEwMTI4OCwtMzA1NDEyNDk0LC02OT
EwMDI2NjddfQ==
-->