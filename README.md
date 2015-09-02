## moodle-tool_uploadcourse-categorypatch

#### Description
This is a patch for Moodle plugin tool_uploadcourse to automatically create categories when a course is uploaded and the categories from the category_path field are missing.

#### Installation
This plugin requires the forked version of uploadcoursecategory [tool_uploadcoursecategory](https://github.com/alexandru-elisei/moodle-tool_uploadcoursecategory), to which a cli script for creating course categories has been added.

This plugin has been tested to work with Moodle 2.9. There are no guarantess it will work with earlier versions.

The basic process involves cloning the repository, then moving the patch.diff file to MOODLE_ROOT_DIRECTORY/admin/tool/uploadcourse/classes:

    git clone https://github.com/alexandru-elisei/moodle-tool_uploadcourse-categorypatch.git # this will create the directory $(pwd)/moodle-tool_uploadcourse-categorypatch
    
    mv "$(pwd)/moodle-tool_uploadcourse-categorypatch/patch.diff" MOODLE_ROOT_DIRECTORY/admin/tool/uploadcourse/classes

replacing MOODLE_ROOT_DIRECTORY with the actual moodle installation root directory path. In the MOODLE_ROOT_DIRECTORY/admin/tool/uploadcourse/classes apply the patch:

    patch helper.php < patch.diff

As an alternative, you can also download the zip file and extract it to the same location, then apply the patch as above.

If you are cloning the git repository, keep in mind that followind the instructions will create the moodle-tool_uploadcourse-categorypatch directory.

#### Usage
When uploading courses from a csv file (from Site administration -> Courses -> Upload courses), the categories specified in the field category_path will be automatically created if they do not exist.

#### Copyright
Copyright (C) Alexandru Elisei 2015 and beyond, All right reserved.

moodle-tool_uploadcourse-categorypatch is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation; either version 3 of the license, or (at your option) any later version.

This software is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of the MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.
