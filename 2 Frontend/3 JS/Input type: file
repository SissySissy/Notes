
## Upload Files

    (() => {
    	const compactUploads = document.querySelectorAll('.upload-compact');
    	compactUploads.forEach(u => {
    		const input = u.querySelector('.input-upload-compact');
    		const preview = u.querySelector('.preview-container');
    
    		input.addEventListener('change', e => {
    			update(e.target.files, preview);
    		});
    	})
    
    	function update(files, preview) {
    		preview.innerHTML = '';
    
    		if(files.length > 0) {
    			preview.innerHTML = `
    				<span><strong>${files[0].name}</strong>(${returnFileSize(files[0].size)})</span>
    				<button class="btn ghost icon warning sm">
    					<i class="fwsj-icon">delete</i>
    				</button>
    			`;
    
    			preview.querySelector('button').addEventListener('click', () => {
    				preview.innerHTML = '';
    			})
    		}
    	}
    
    	function returnFileSize(number) {
    	  if (number < 1024) {
    	    return number + ' bytes';
    	  } else if (number >= 1024 && number < 1048576) {
    	    return (number / 1024).toFixed(1) + ' KB';
    	  } else if (number >= 1048576) {
    	    return (number / 1048576).toFixed(1) + ' MB';
    	  }
    	}
    
    })();

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNTkyNTc4MzksLTE1MDg1NDU5NzVdfQ
==
-->