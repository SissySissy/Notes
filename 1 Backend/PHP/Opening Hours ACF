# Opening Hours ACF
    <?php
    
    // Prepare Data
    $openingHours = get_field('opening_hours_regular', 'option');
    $indexWeekDays = array('monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday', 'sunday');
    $flatOpeningHours = array();
    $displayGroups = array();
    
    
    foreach($indexWeekDays As $day) {
    	$found_day = false;
    	foreach($openingHours As $rowId => $block) {
    		$key = array_search($day, array_column($block['days'], 'value'));
    		if($key !== false) {
    			$flatOpeningHours[] = [
    				'key' => substr(date( 'D', strtotime($day) ), 0, 2),
    				'label' => date_i18n( 'l', strtotime($day) ),
    				'rowId' => $rowId,
    				'open' => true
    			];
    			$found_day = true;
    			break;
    		}
    	}
    	if(!$found_day) {
    		$flatOpeningHours[] = [
    			'key' => substr(date( 'D', strtotime($day) ), 0, 2),
    			'label' => date_i18n( 'l', strtotime($day) ),
    			'rowId' => -1,
    			'open' => false
    		];
    	}
    }
    
    $lastRowId = Null;
    $groupId = -1;
    foreach($flatOpeningHours As $day) {
    	if($day['rowId'] !== $lastRowId) {
    		$groupId++;
    		$displayGroups[$groupId] = [];
    		$lastRowId = $day['rowId'];
    	}
    	$displayGroups[$groupId][] = $day;
    }
    
    // Output template
    foreach($displayGroups As $group) {
    	if(
    		($group[0]['key'] === 'Su' || $group[0]['key'] === 'Sa') &&
    		!$group[0]['open']
    	) {
    		continue;
    	}
    	$length = count($group);
    	$open = $group[0]['open'];
    	$firstDay = $group[0];
    	$lastDay = $group[$length - 1];
    	$hours = $open ? $openingHours[$firstDay['rowId']]['hours'] : array();
    
    	$hoursStrings = array();
    	foreach($hours As $index => $hour) {
    		$hoursStrings[] = $hour['from'] . '–' . $hour['to'];
    	}
    
    	$daysLabel = $length === 1 ? $firstDay['label'] : $firstDay['label'] . ' - ' . $lastDay['label'];
    	$daysKey = $length === 1 ? $firstDay['key'] : $firstDay['key'] . '-'. $lastDay['key'];
    
    	echo '<p><span class="hours-label">' . $daysLabel . '</span><br>';
    	if($open) {
    		echo '<span class="hours-value" itemprop="openingHours" content="' . $daysKey . ' ' . implode(' ', $hoursStrings) . '">' . implode('<br>', $hoursStrings) . '</span>';
    	} else {
    		echo '<span>' . __('closed', 'matter') . '</span>';
    	}
    	echo '</p>';
    }
    
    
    
    ?>

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MjMzMzI0MzEsMTA4NjEwODg3N119
-->