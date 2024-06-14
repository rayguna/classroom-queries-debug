# classroom-queries-debug

Target: https://classroom-queries-debug.matchthetarget.com/

Link to video: https://share.descript.com/view/hRpXMDoQJDT

Link to notes:  https://learn.firstdraft.com/lessons/128

<hr>

Notes:

1. The first time I ran the command bin/dev, I got an erorr message. Deleting and recreating the codespace fixed the issue. 
2. Checked to make sure all hyperlinks (courses, departments, and students) are working and fixed accordingly.
3. Check if database is empty or not by navigating to https://fuzzy-engine-x957x7gvp64fvggr-3000.app.github.dev/rails/db. Just append /rails/db to the url. Review each table. You could either create the data using the web interface or via ruby terminal using the command `rake sample_data`. When you check back on the database tables, you will find that they are no longer empty.
4. Although the database tables are populated, the table values are not displayed on the web pages. Fixed typos in the code to correctly display the tables contents. 
5. Checked to make sure all buttons are working and fixed accordingly.
6. Checked to make sure all hyperlinks in the table are working.
7. Remember to parse array values that are extracted from a database:

```
#views/courses/show.html.erb

  def show
    the_id = params.fetch("path_id")
    @department = Department.all.where({:id => the_id })[0]

    render({ :template => "departments/show" })
  end
```

8. Remember to save often. To return to the last commit and discard all recent changes, type in the terminal git reset -hard HEAD.

9. In the config/routes.rb, the function get should have been post:

```
post("/insert_course", { :controller => "courses", :action => "create" })
```
