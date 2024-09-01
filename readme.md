


# lib_GoogleDrive

This is the Google Drive Connector for Convertigo. use this library to connect to your no code apps to Google Drive


For more technical informations : [documentation](./project.md)

- [Installation](#installation)
- [Sequences](#sequences)
    - [checkAccessTokenGoogle](#checkaccesstokengoogle)
    - [ClearRefreshToken](#clearrefreshtoken)
    - [FileList](#filelist)
    - [formssource_ListFiles](#formssource_listfiles)
    - [getRefreshToken](#getrefreshtoken)
    - [loginGoogleWithCode](#logingooglewithcode)
    - [TestLogin](#testlogin)
- [Mobile Library](#mobile-library)
    - [Pages](#pages)
        - [Configure](#configure)
        - [TestOnly](#testonly)


## Installation

1. In your Convertigo Studio click on ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/icons/studio/project_import.gif?raw=true "Import a project in treeview") to import a project in the treeview
2. In the import wizard

   ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/tomcat/webapps/convertigo/templates/ftl/project_import_wzd.png?raw=true "Import Project")
   
   paste the text below into the `Project remote URL` field:
   <table>
     <tr><td>Usage</td><td>Click the copy button at the end of the line</td></tr>
     <tr><td>To contribute</td><td>

     ```
     lib_GoogleDrive=https://github.com/convertigo/c8oprj-lib-googledrive.git:branch=master
     ```
     </td></tr>
     <tr><td>To simply use</td><td>

     ```
     lib_GoogleDrive=https://github.com/convertigo/c8oprj-lib-googledrive/archive/master.zip
     ```
     </td></tr>
    </table>
3. Click the `Finish` button. This will automatically import the __lib_GoogleDrive__ project


## Sequences

### checkAccessTokenGoogle

Checks is a valid access token is held by the current users' session for Google

This as to be called by client apps to decide whenever or not they have to display an OAuth login screen



### ClearRefreshToken

Remove any RefreshToken and GoogletAcessTokne form the session and user profile

### FileList

List files in the current logged user google drive

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>pageSize</td><td>The Max number of items to return (Default 100)</td>
</tr>
<tr>
<td>q</td><td>The search query string. See  https://developers.google.com/drive/api/guides/search-files for examples</td>
</tr>
</table>

### formssource_ListFiles

List files from a Google Drive. You can filter files to list using the Query variable

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>forms_config</td><td>Returns the file list of a drive with a given configuration</td>
</tr>
<tr>
<td>forms_PageSize</td><td>The maximum number of items to return</td>
</tr>
<tr>
<td>forms_Query</td><td>The search query to perform. An empty string wll return all files. See this link for search query syntax : <a href='https://developers.google.com/drive/api/guides/search-files' target='_blank'>Query</a></td>
</tr>
</table>

### getRefreshToken

Gets the google oAuth refresh token previsously stored in user profile. Used  to get the rToken  to be stored in the  Forms data source configuration 

### loginGoogleWithCode

Perform the OAuth flow for Google

If the token is valid, it will be stored in the user's session to be used when calling Microsoft APIs.

Also if the token is valid, setAuthenticatedUser step is executed to flag this session as authenticated.


**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>client_id</td><td></td>
</tr>
<tr>
<td>code</td><td></td>
</tr>
<tr>
<td>keySecret</td><td></td>
</tr>
<tr>
<td>redirect_uri</td><td></td>
</tr>
</table>

### TestLogin

This only to have the test application logged in to be able to add Attributes to user accounts

## Mobile Library

### Pages

#### Configure

The No Code forms configuration page

#### TestOnly

This is a Test page to launch before calling BackEnd seqeunces. This will login using the DEMO user profile



