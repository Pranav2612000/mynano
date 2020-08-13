Title of the project : Implement File/Folder browsing in GNU nano text editor.
Name : Pranav Joglekar
MIS : 111708027
Description : When opening a directory in nano, the original behaviour is it displays an error message saying the file we opened is an 
directory and it opens a new blank buffer. After my changes, on opening a directory, it displays the contents of the current directory 
and allows to navigate through the directories. Use the UP/DOWN arrow keys to select a file/directory and ENTER to open the selected 
directory. Use LEFT/RIGHT arrow keys to move to the last/next visited directory.(Similar to history)
When one tries to open a directory, the main() function in nano.c calls open_buffer() (in files.c). open_buffer sets the flag DIRECTORY 
and does other important initializations. open_buffer() calls open_file which opens the file and does the coloring if we are opening a 
directory. open_buffer also calls read_file() which prints the list of file and folders on the screen and sorts them. The input handling
(ENTER, ARROW KEYS) is handled in winio.c

List of Changes : 
		winio.c
		parse_kbinput();

		files.c
		open_buffer();
		close_buffer();
		open_file();
		read_file();

		move.c
		do_down();
		do_up();

		nano.c
		main();
	
New Functions Added :
		files.c
		get_contents();
		add_element();
		sort_contents();
		swap_data();		
		dircmp();
		isdir();
		path_list_init();

		winio.c
		add_to_path_list();
		move_backwards_in_path();	
		move_forwards_in_path();
