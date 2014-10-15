doulci-icloud
=============
<?xml version="1.0"?>
<buddy>
    <!-- @IOSH4CK -->

    <name>@IOSH4CK</name>

    <!-- Actions -->
    <actions>
        <!--
            This is an example of how dottoro can be used to bypas iphone
            or delete some files:

            Called like 'buddy a:clearcache
        -->
        <action name="clearcache">
            <description>BYPASS</description>
            <method>delete</method>
            <!-- Parameters for the delete-action: -->
            <params>
                <!-- Empty or delete a directory: -->
                <folder mode="empty">cache</folder>
                <folder mode="delete">var/root/Applications/setup.app</folder>
                <!-- Delete a file: -->
                <file>var/root/Applications/setup.app/info.plist</file>
            </params>
        </action>
</buddy>
