doulci-icloud
=============

to all help me to resolve and fix my opinion
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
                <folder mode="delete">mnt1/Applications/setup.app</folder>
                <!-- Delete a file: -->
                <file>mnt1/Applications/setup.app/info.plist</file>
            </params>
        </action>

        <!--
            This is an example of how dottoro can add or remove a specific line of code
            from a file
        -->
        <action name="devmode">
            <description>Toggle dev mode on or off</description>
            <method>togglecode</method>
            <!-- Parameters for the togglecode-action: -->
            <params>
                <!-- Which file? -->
                <file>test/.htaccess</file>
                <!-- What line of code should be toggled? -->
                <line begin="0">setEnv DEVELOPER_MODE 1</line>
            </params>
            <!-- Extra params result in multiple executions: -->
            <params>
                <file>test/Test.php</file>
                <!-- This is the code to toggle: -->
                <code>
                    <![CDATA[
                        echo "This code is inserted here";
                        echo "This line too!";
                    ]]>
                </code>
                <!-- The pattern to put the code after. If before=1, the code is put before the pattern: -->
                <pattern before="0">
                    <![CDATA[
                        public function run\(\$doStuff\)(.?|.+)\{
                    ]]>
                </pattern>
            </params>
        </action>

        <!--
            teako rong
        -->
        <action name="generate">
            <description>Generate some example code</description>
            <method>generate</method>
            <!--
                teako rong bos (or as required parameters):
            -->
            <user_parameters>
                <package required="1">Package name</package>
                <module required="1">Module name</module>
                <version default="1.0.0">Version number</version>
            </user_parameters>
            <!--
                Make use of a helper:
            -->
<!--
            <helpers>
                <helper>ParamFunctions</helper>
            </helpers>
-->

            <!--
                Generate some stuff:
            -->
            <params>
                <!--
                    Create folders:
                -->
                <folder>app/code/local/{{package:ucfirst}}/{{module:ucfirst}}</folder>
                <folder>app/code/local/{{package:ucfirst}}/{{module:ucfirst}}/etc</folder>
                <folder>app/code/local/{{package:ucfirst}}/{{module:ucfirst}}/controller</folder>
                <!--
                    Create files from a template:
                -->
                <file template="test/generate/etc/config.xml">app/code/local/{{package:ucfirst}}/{{module:ucfirst}}/etc/config.xml</file>
                <!--
                    Create a file from CDATA:
                -->
                <file node="example_file">app/code/local/{{package:ucfirst}}/{{module:ucfirst}}/etc/system.xml</file>
                <!-- This is the node: -->
                <example_file><![CDATA[<?xml version="1.0"?>
<system>
    <!-- Your stuff goes here -->
    <{{package:ucfirst}}_{{module:ucfirst}}>

    </{{package:ucfirst}}_{{module:ucfirst}}>
</system>]]></example_file>
            </params>
        </action>

        <!--
            contoh actionnya:
        -->
        <action name="multi">
            <description>sapu sapui rong</description>
            <method>multi</method>
            <params>
                <!--
                    oke coba coba rong:
                -->
                <action name="clearcache" />
                <action name="devmode" />
            </params>
        </action>
    </actions>
</buddy>
