<h1>API Testing Project for Spotify</h1>

The scope of this project is to use all API knowledge gained throught the Software Testing course and apply them in practice, using a live application.
The purpose of the testing is to evaluate the Spotify API on a PC using Google Chrome, without extending the tests to mobile platforms such as iOS, Android, or iPhone.

Application under test: spotify.com

Tools used: Postman, Newman

Collection link: [Postman Collection](https://github.com/RamonaNico/Manual-Testing-API-Project-Spotify/blob/main/Spotify%20Project.postman_collection.json)

Documentation link: [Spotify Documentation](https://developer.spotify.com/documentation/web-api)

How to Use:
1. Importing the Collection into Postman:
 - Open Postman.
 - Select Import from the top left corner.
 - Choose Upload Files and select the Spotify_Project.postman_collection.json file downloaded from this repository.
2. Importing the Environment into Postman:
 - Open Postman.
 - Navigate to Environments in the left sidebar.
 - Click on Import and upload the Spotify.postman_environment.json file obtained from this repository.
3. Configuring Authentication
 - Open the imported environment in Postman.
 - Locate and edit the environment variables:
     - client_id: Enter your Spotify Developer client ID.
     - client_secret: Enter your Spotify Developer client secret.
     - refreshed_token: If applicable, set the access token generated from your Spotify Developer account or obtain it through the OAuth 2.0 authentication flow.


<h2>Tests performed</h2>

<ol>
<li>Create Private Playlist - valid fields</li>

HTTP method for request: POST<br>
Request description: It creates a playlist for a Spotify user and it checks the status, the playlist's name, description, if the playlist is not public, owner type and track limit.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 201 Created<br>

Below you can find a picture of the API request from Postman:<br>

![1  B Create Private PL valid fields](https://github.com/user-attachments/assets/d457dcba-ab76-4383-9b7f-beafd08a9b45)<br>


JavaScript Tests:

![1  T1 Create Private PL valid fields](https://github.com/user-attachments/assets/3f861db5-ce5c-4105-b04b-57b76ccad715)<br>

![1  T2 Create Private PL valid fields](https://github.com/user-attachments/assets/846fa1a9-1382-4e76-b420-db8f4a05aa0d)<br>

![1  T3 Create Private PL valid fields](https://github.com/user-attachments/assets/06457c13-6451-44f5-94ac-8b2d541033a4)<br>


<li>Create Playlist - 100 char name</li>

HTTP method for request: POST<br>
Request description: It creates a playlist for a Spotify user and the name of the playlist contains 100 characters.<br>
Test types / techniques used: Functional Testing, Negative Testing, Boundary Testing<br>
Response status code: 201 Created<br>

Below you can find a picture of the API request from Postman:<br>

![2  B 100 char name](https://github.com/user-attachments/assets/fb781da2-1a15-47af-b8ae-d03b3fbaf4ea)<br>

JavaScript Tests:

![2  T 100 char name](https://github.com/user-attachments/assets/baae4340-50a8-41d9-9aae-1b8d886be9d0)<br>

<li>Create Playlist - no name</li>

HTTP method for request: POST<br>
Request description: It tries to create a playlist for a Spotify user without specifying a name.<br>
Test types / techniques used: Negative Testing, Behavior Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![3  B no name](https://github.com/user-attachments/assets/7b742f63-87c7-47ea-8a88-16d9375ccc11)<br>

JavaScript Tests:

![3  T no name](https://github.com/user-attachments/assets/382ad1ec-1e66-48c6-9be8-82b7140bd4ee)<br>

<li>Add Items to Playlist - present snapshot id</li>

HTTP method for request: POST<br>
Request description: It adds items to a playlist and it verifies that the body response contains snapshot_id.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 201 Created<br>

Below you can find a picture of the API request from Postman:<br>

![1  B present snapshot id](https://github.com/user-attachments/assets/1c741998-c0a4-4163-831d-ec5ae77a1ef9)<br>

JavaScript Tests:

![1  T present snapshot id](https://github.com/user-attachments/assets/b8cdd763-7161-41c9-b240-a0dfa3438b07)<br>

<li>Add Items to Playlist - string snapshot id</li>

HTTP method for request: POST<br>
Request description: It adds items to a playlist and it verifies that snapshot_id returned in the body is a string.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 201 Created<br>

Below you can find a picture of the API request from Postman:<br>

![2  B string snapshot id](https://github.com/user-attachments/assets/35af0ea3-83ca-4ad0-9270-eb91e7c69d59)<br>

JavaScript Tests:

![2  T string snapshot id](https://github.com/user-attachments/assets/b159aa73-4a31-4c12-8132-70d455bbb42e)<br>

<li>Add Items to Deleted Playlist - status</li>

HTTP method for request: POST<br>
Request description: It adds items to a playlist that has been manually deleted from the UI and it checks the status.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 201 Created<br>

Below you can find a picture of the API request from Postman:<br>

![3  B add it to dltd pl status](https://github.com/user-attachments/assets/e47ebae3-1d5c-4242-8f50-c21a8431a640)<br>

JavaScript Tests:

![3  T add it to dltd pl status](https://github.com/user-attachments/assets/fb73275a-d6d2-49a3-9deb-c2c8c53968ef)<br>

<li>Add Items to Playlist - no token</li>

HTTP method for request: POST<br>
Request description: It tries to add items to a playlist without providing the token.<br>
Test types / techniques used: Security Testing, Negative Testing<br>
Response status code: 401 Unauthorized<br>

Below you can find a picture of the API request from Postman:<br>

![4  B no token](https://github.com/user-attachments/assets/a653ccd8-5d1e-45bd-a6ca-6fa84ed321d2)<br>

JavaScript Tests:

![4  T no token](https://github.com/user-attachments/assets/dd6bb78f-6029-46ae-8bf0-d9d6fdeaf998)<br>

<li>Add Items to Playlist - invalid track URI</li>

HTTP method for request: POST<br>
Request description: It tries to add items to a playlist without providing a valid track URI.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![5  B invalid track URI](https://github.com/user-attachments/assets/a201d313-7f42-4507-9f7d-49bb69d05f53)<br>

JavaScript Tests:

![5  T invalid track URI](https://github.com/user-attachments/assets/675960a3-ba91-4f33-aafc-d98af3ccfa09)<br>

<li>Add Items to Playlist - empty body</li>

HTTP method for request: POST<br>
Request description: It tries to add items to a playlist without providing a request body.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![6  B empty body](https://github.com/user-attachments/assets/5a169172-6afc-4cf0-bb0c-5091446c3545)<br>

JavaScript Tests:

![6  T empty body](https://github.com/user-attachments/assets/33bec986-e514-4764-bcba-bb566b2577b7)<br>

<li>Add Items to Playlist - no track URI</li>

HTTP method for request: POST<br>
Request description: It tries to add items to a playlist without providing a track URI.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![7  B no track URI](https://github.com/user-attachments/assets/8d469dec-0b3b-4d8b-8fb6-da8a9ffd7ad7)<br>

JavaScript Tests:

![7  T no track URI](https://github.com/user-attachments/assets/434e95d4-0d68-40a1-be09-358de53c5206)<br>

<li>Add Duplicate Item to Playlist - status</li>

HTTP method for request: POST<br>
Request description: It adds to a playlist an item that has been added before to the same playlist.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 201 Created<br>

Below you can find a picture of the API request from Postman:<br>

![8  B duplicate it status](https://github.com/user-attachments/assets/5c1574ff-1b24-4338-85a0-00ce2abd0d2a)<br>

JavaScript Tests:

![8  T duplicate it status](https://github.com/user-attachments/assets/5eeb04db-b996-422e-b857-0a16dfa2c70f)<br>

<li>Get Playlist Items - response time</li>

HTTP method for request: GET<br>
Request description: It gets full details of the items of a playlist owned by a Spotify user and it checks the response time.<br>
Test types / techniques used: Performance Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![1  B Get PL Items response time](https://github.com/user-attachments/assets/3e44f8db-f68b-412d-8458-01c1174f2874)<br>

JavaScript Tests:

![1  T Get PL Items response time](https://github.com/user-attachments/assets/a7f9e4f0-7ce6-40c2-baf8-5ac60306afab)<br>

<li>Get Deleted Playlist Items - status</li>

HTTP method for request: GET<br>
Request description: It gets full details of the items of a playlist even if the items have been removed.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![2  B deleted pl it](https://github.com/user-attachments/assets/74709b29-030f-49fb-88b9-5096de33474c)<br>

JavaScript Tests:

![2  T deleted pl it](https://github.com/user-attachments/assets/288fc46e-8910-4898-bfbb-602cd08e4417)<br>

<li>Get Current User's Playlists - status</li>

HTTP method for request: GET<br>
Request description: It gets a list of the playlists owned or followed by the current Spotify user.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![3  B current user pl](https://github.com/user-attachments/assets/c20cff38-92ed-439e-9e86-d0f991d92992)<br>

JavaScript Tests:

![3  T current user pl](https://github.com/user-attachments/assets/1b3e49e4-9257-49cf-bf03-84c4744484ef)<br>

<li>Change Playlist Details - expired token</li>

HTTP method for request: PUT<br>
Request description: It tries to change a playlist's name and public/private state providing an expired token.<br>
Test types / techniques used: Functional Testing, Security Testing, Negative Testing<br>
Response status code: 401 Unauthorized<br>

Below you can find a picture of the API request from Postman:<br>

![1  B expired token](https://github.com/user-attachments/assets/be289e54-1e9b-4936-b6d6-139e21577ac1)<br>

JavaScript Tests:

![1  T expired token](https://github.com/user-attachments/assets/cf6c1884-92a1-4f77-9330-a6decf7ce5d3)<br>

<li>Change Playlist Details - status</li>

HTTP method for request: PUT<br>
Request description: It changes a playlist's name and public/private state. The playlist must be owned by the user.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![2  B status](https://github.com/user-attachments/assets/822bc472-902b-40a9-8a0d-022db053c198)<br>

JavaScript Tests:

![2  T status](https://github.com/user-attachments/assets/c0f6f25e-991c-4305-8f13-123471c873fd)<br>

<li>Get Updated Playlist</li>

HTTP method for request: GET<br>
Request description: It gets a playlist owned by a Spotify user.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![4  B Get Updated PL](https://github.com/user-attachments/assets/9b4f21c4-e41b-4c55-82ac-c3fc274e4e59)<br>

JavaScript Tests:

![4  T Get Updated PL](https://github.com/user-attachments/assets/ada0272d-2561-4122-a2b9-52d13d6b0738)<br>


<li>Change Playlist Details - empty body response</li>

HTTP method for request: PUT<br>
Request description: It checks that the body response is empty when the user changes the playlist details.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![3  B empty body response](https://github.com/user-attachments/assets/61f3a537-1cc1-4377-a0f5-3bcda63652f4)<br>

JavaScript Tests:

![3  T empty body response](https://github.com/user-attachments/assets/aa9957f6-6376-425e-9af0-e3d1c2fe4aca)<br>

<li>Remove Playlist Items - present snapshot id string</li>

HTTP method for request: DELETE<br>
Request description: It removes one or more items from a user's playlist and it checks if the response body contains a snapshot id which is a string.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![1  B Remove PL It present snapshot id string](https://github.com/user-attachments/assets/9b629de5-a674-49b8-a478-2e1f36ea408c)<br>

JavaScript Tests:

![1  T Remove PL It present snapshot id string](https://github.com/user-attachments/assets/1baafe88-0623-4885-b9af-281a3787641a)<br>

<li>Remove Playlist Items - position based</li>

HTTP method for request: DELETE<br>
Request description: It removes one or more items from a user's playlist based on the item position indicated.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![2  B position based](https://github.com/user-attachments/assets/6532224b-bf25-46b4-bc6b-73ce058eda21)<br>

JavaScript Tests:

![2  T position based](https://github.com/user-attachments/assets/a9663204-56af-45d4-b620-002aef4a3b71)<br>

<li>Remove Playlist Items - incorrect position</li>

HTTP method for request: DELETE<br>
Request description: It tries to remove one or more items from a user's playlist indicating an incorrect item position.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![3  B incorrect position](https://github.com/user-attachments/assets/327d702b-6a81-474e-b2c4-30b8cd3c9fa4)<br>

JavaScript Tests:

![3  T incorrect position](https://github.com/user-attachments/assets/a55e21e8-da3c-4fc8-8f58-7dda147a1578)<br>

<li>Remove Playlist Items - invalid position</li>

HTTP method for request: DELETE<br>
Request description: It tries to remove one or more items from a user's playlist indicating an invalid item position.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![4  B invalid position](https://github.com/user-attachments/assets/8dd16a29-7622-4c04-81b4-e7c7ce654005)<br>

JavaScript Tests:

![4  T invalid position](https://github.com/user-attachments/assets/a1036ae2-f054-4c5b-b039-8f8264ef3546)<br>

<li>Remove Playlist Items - invalid URI</li>

HTTP method for request: DELETE<br>
Request description: It tries to remove one or more items from a user's playlist indicating an invalid track URI.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![5  B invalid URI](https://github.com/user-attachments/assets/bc7219ea-afd4-488d-9944-e1e23d20977a)<br>

JavaScript Tests:

![5  T invalid URI](https://github.com/user-attachments/assets/8362f82b-8a48-4652-b13e-589eb5c161e9)<br>

<li>Remove Playlist Absent Items</li>

HTTP method for request: DELETE<br>
Request description: It tries to remove one or more items which have never been added to the user's playlist.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![6  B absent items](https://github.com/user-attachments/assets/e2318344-403b-466a-ad89-bd9d8e0c1c0c)<br>

JavaScript Tests:

![6  T absent items](https://github.com/user-attachments/assets/cd43c5e8-3f8e-4225-a315-ce49929e61d5)<br>

<li>Remove Playlist Duplicate Items</li>

HTTP method for request: DELETE<br>
Request description: It removes one or more items which have been added to the user's playlist multiple times.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![7  B duplicate items](https://github.com/user-attachments/assets/e84e0a29-ba9d-4514-995d-41f4da571851)<br>

JavaScript Tests:

![7  T duplicate items](https://github.com/user-attachments/assets/50cdd828-5b6d-4456-9bb6-da8610e273ff)<br>

<li>Remove Playlist Items - incorrect method</li>

HTTP method for request: GET<br>
Request description: It tries to remove one or more items from the user's playlist using an incorrect HTTP method.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![5  B incorrect method](https://github.com/user-attachments/assets/3ca538c0-de8c-4452-9f18-f98586a76012)<br>

JavaScript Tests:

![5  T incorrect method](https://github.com/user-attachments/assets/fd6be87f-b817-40cc-91b5-566a4ecad372)<br>

<li>Get Artist - valid fields</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies the artist's URL, followers count, popularity and uri.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![B Get Artist valid fields](https://github.com/user-attachments/assets/42a30d8a-f8fd-4220-9511-c41de070390d)<br>

JavaScript Tests:

![T1 Get Artist valid fields](https://github.com/user-attachments/assets/8eeb4a7a-1643-4356-ab54-73f20d10cd9f)<br>

![T2 Get Artist valid fields](https://github.com/user-attachments/assets/9b4106c4-a188-4ac6-87d9-3eff3516657b)<br>

<li>Get Artist - response time</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies the response time.<br>
Test types / techniques used: Functional Testing, Performance Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![2  B response time](https://github.com/user-attachments/assets/9c73a3e8-ea14-48e3-8400-8d2f6d960397)<br>

JavaScript Tests:

![2  T response time](https://github.com/user-attachments/assets/84807777-1bb8-4591-867c-f346f17b78d4)<br>

<li>Get Artist - header present</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies if the response contains the correct header "Content-Type".<br>
Test types / techniques used: Functional Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![3  B header present](https://github.com/user-attachments/assets/d150ea5c-75c5-427b-92e4-1658043eabbb)<br>

JavaScript Tests:

![3  T header present](https://github.com/user-attachments/assets/2209083a-0d66-478a-8607-3c04f1c7399d)<br>

<li>Get Artist - valid artist name</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies if the artist's name is correct and valid.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![4  B valid artist name](https://github.com/user-attachments/assets/dcacd0b1-2137-46b3-9cf7-2a5a2421e52c)<br>

JavaScript Tests:

![4  T valid artist name](https://github.com/user-attachments/assets/7e63eaa1-43c4-42f5-8a75-4a2213986b60)<br>

<li>Get Artist - invalid artist name</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies if the artist's name is correct.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![5  B invalid artist name](https://github.com/user-attachments/assets/cc0f4d7d-0537-4b3b-990b-262bab584767)<br>

JavaScript Tests:

![5  T invalid artist name](https://github.com/user-attachments/assets/f7c64f4d-3242-4586-9c3b-23aa009f45ba)<br>

<li>Get Artist - valid genres</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies if the genres are correct and valid.<br>
Test types / techniques used: Functional Testing, Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![6  B valid genres](https://github.com/user-attachments/assets/e0526ebb-da31-44b1-bb07-0ed5da8a763f)<br>

JavaScript Tests:

![6  T valid genres](https://github.com/user-attachments/assets/7c200d2f-1785-4dc5-bba5-8ff4e5b483c3)<br>

<li>Get Artist - response JSON</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies the response structure in the Postman console.<br>
Test types / techniques used: Functional Testing, Integration Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![7  B response json](https://github.com/user-attachments/assets/6cd1632c-c953-4050-bd8c-0fb431df7fc2)<br>

JavaScript Tests:

![7  T response json](https://github.com/user-attachments/assets/9e793757-5499-486e-ac88-b2c3a992d356)<br>

<li>Get Artist - all fields present</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information for a single artist identified by their unique Spotify ID and it verifies if the response contains all the required fields.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![8  B all fields present](https://github.com/user-attachments/assets/ecbce59c-c616-4977-ab66-759a1a719861)<br>

JavaScript Tests:

![8  T all fields present](https://github.com/user-attachments/assets/70bf87f2-183a-4a94-97fb-199e0af413f8)<br>

<li>Search Tracks - response time</li>

HTTP method for request: GET<br>
Request description: It gets the Spotify catalog information about tracks that match a keyword string and it checks the response time.<br>
Test types / techniques used: Functional Testing, Performance Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![1  B response time](https://github.com/user-attachments/assets/9e6be6b9-33b2-4a5e-8ddb-bbdaa0f7e467)<br>

JavaScript Tests:

![1  T response time](https://github.com/user-attachments/assets/b1aa6c6b-13cd-40d6-b6ef-5b6be28a0c1d)<br>

<li>Search Tracks - invalid limit value 0</li>

HTTP method for request: GET<br>
Request description: It tries to get the Spotify catalog information about tracks that match a keyword string when the limit parameter is set to 0 (invalid value).<br>
Test types / techniques used: Functional Testing, Negative Testing, Equivalence Partitioning, Boundary Value Analysis<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![2  B invalid limit 0](https://github.com/user-attachments/assets/7fac25b2-3855-432f-9371-2ead07e90317)<br>

JavaScript Tests:

![2  T invalid limit 0](https://github.com/user-attachments/assets/ffa62666-d487-42b8-8a82-6e4b76d51b4e)<br>

Parameters:

![2  P invalid limit 0](https://github.com/user-attachments/assets/26324e53-3c09-42b6-8180-2c3aeb019bed)<br>

<li>Search Tracks - invalid limit value 51</li>

HTTP method for request: GET<br>
Request description: It tries to get the Spotify catalog information about tracks that match a keyword string when the limit parameter is set to 51 (invalid value).<br>
Test types / techniques used: Functional Testing, Negative Testing, Equivalence Partitioning, Boundary Value Analysis<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![3  B invalid limit 51](https://github.com/user-attachments/assets/fc37a678-cf28-4ada-9105-d8957936a737)<br>

JavaScript Tests:

![3  T invalid limit 51](https://github.com/user-attachments/assets/09b7bf45-3f9b-4aae-a540-ff47318876e5)<br>

Parameters:

![3  P invalid limit 51](https://github.com/user-attachments/assets/b67f8bc9-c39d-4746-9e8a-c6abf3e026b2)<br>

<li>Search Tracks - invalid type limit value "a"</li>

HTTP method for request: GET<br>
Request description: It tries to get the Spotify catalog information about tracks that match a keyword string when the limit parameter is set to the letter "a" instead of a number (invalid type value).<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![4  B invalid type limit](https://github.com/user-attachments/assets/e86cd4a6-b6f6-431b-bde7-c0f285e723c9)<br>

JavaScript Tests:

![4  T invalid type limit](https://github.com/user-attachments/assets/c51eee6c-be63-4bb4-9ded-03b3ce6c5015)<br>

Parameters:

![4  P invalid type limit](https://github.com/user-attachments/assets/11aa2c5e-2bf4-4029-820d-890802e06659)<br>

<li>Search Tracks - no q parameter</li>

HTTP method for request: GET<br>
Request description: It tries to get the Spotify catalog information about tracks that match a keyword string without setting a required parameter.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![5  B no q param](https://github.com/user-attachments/assets/a55c3c0f-3362-4d54-8fa0-4405aae0b8a0)<br>

JavaScript Tests:

![5  T no q param](https://github.com/user-attachments/assets/2295552f-c007-4241-86e1-be32474f16ca)<br>

Parameters:

![5  P no q param](https://github.com/user-attachments/assets/a1c473de-cba3-4c07-b98c-b44bf682025b)<br>

<li>Search Tracks - no type parameter</li>

HTTP method for request: GET<br>
Request description: It tries to get the Spotify catalog information about tracks that match a keyword string without setting a required parameter.<br>
Test types / techniques used: Functional Testing, Negative Testing<br>
Response status code: 400 Bad Request<br>

Below you can find a picture of the API request from Postman:<br>

![6  B no type param](https://github.com/user-attachments/assets/795a4401-d76f-4e50-ae1b-9bca72c69b55)<br>

JavaScript Tests:

![6  T no type param](https://github.com/user-attachments/assets/1ef2e0d0-0495-4b08-9156-c7f02e6023fa)<br>

Parameters:

![6  P no type param](https://github.com/user-attachments/assets/870dfaea-db7e-4507-adff-b412b6b5a64c)<br>

<li>Follow Artists - status</li>

HTTP method for request: PUT<br>
Request description: It adds the current user as a follower of one artist and it checks the status.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 204 No Content<br>

Below you can find a picture of the API request from Postman:<br>

![1  B status](https://github.com/user-attachments/assets/cd416ffa-f752-443f-a908-c1ca4f8f49f0)<br>

JavaScript Tests:

![1  T status](https://github.com/user-attachments/assets/33dedafd-5de2-4370-bda6-78b060fe68ea)<br>

<li>Follow Artists - response time</li>

HTTP method for request: PUT<br>
Request description: It adds the current user as a follower of one artist and it checks the response time.<br>
Test types / techniques used: Functional Testing, Performance Testing<br>
Response status code: 204 No Content<br>

Below you can find a picture of the API request from Postman:<br>

![2  B response time](https://github.com/user-attachments/assets/e0ecc695-b270-4a26-a086-c6be6aae2fe9)<br>

JavaScript Tests:

![2  T response time](https://github.com/user-attachments/assets/7361e4ea-9025-455a-bb86-c317594a0e33)<br>

<li>Follow Artists - empty body response </li>

HTTP method for request: PUT<br>
Request description: It adds the current user as a follower of one artist and it checks if the response body is empty.<br>
Test types / techniques used: Functional Testing<br>
Response status code: 204 No Content<br>

Below you can find a picture of the API request from Postman:<br>

![3  B empty body](https://github.com/user-attachments/assets/28a1a178-7ed7-4c07-9896-7f1cc41f5f78)<br>

JavaScript Tests:

![3  T empty body](https://github.com/user-attachments/assets/715f9f52-fff5-42c9-a0f8-f9b8a93a6f4f)<br>

<li>Follow Artists - no token</li>

HTTP method for request: PUT<br>
Request description: It tries to add the current user as a follower of one artist without providing a token.<br>
Test types / techniques used: Security Testing<br>
Response status code: 401 Unauthorized<br>

Below you can find a picture of the API request from Postman:<br>

![4  B no token](https://github.com/user-attachments/assets/cecf9247-e3bb-45df-a006-4076cdc05ef6)<br>

JavaScript Tests:

![4  T no token](https://github.com/user-attachments/assets/ece0c4bd-0f92-43b9-9709-43c9817b8179)<br>

</ol>

<h2>Execution report for the created API collection </h2>

Below you can find the execution report that was generated through Newman directly from the terminal. <br>

![raport tabel](https://github.com/user-attachments/assets/c303f64e-2795-4a1e-890e-f4c33ce77b8b)<br>

<h2>Defects found</h2>

The following issues were identified while running the postman tests:<br>

Test Case 1: Playlist Name Exceeding Character Limit Allows Creation (Status Code 201)

Summary:
Creating a playlist with a name containing 100 characters results in a successful response (status code 201), but it should return a different status code.

Preconditions:
- A PC with Google Chrome browser.
- A valid Spotify account.
- The Postman tool installed and opened.
- Proper authentication to access the Spotify API.

Steps to Reproduce:

Send the following request:
curl --request POST \
  --url https://api.spotify.com/v1/users/{user_id}/playlists \
  --header 'Authorization: Bearer {refreshed_token}' \
  --header 'Content-Type: application/json' \
  --data '{
    "name": "vvvvvvvvvvbbbbbbbbbbaaaaaaaaaabbbbbbbbbbaaaaaaaaaabbbbbbbbbbaaaaaaaaaabbbbbbbbbbaaaaaaaaaabbbbbbbbbb",
    "description": "My Best Music",
    "public": false
}'

Expected Results:
The API should return a status code different from 201, indicating that the playlist name exceeds the allowed character limit.

Actual Results:
The API returns a status code 201, indicating that the playlist was created successfully despite the name exceeding the expected character limit.


Test Case 2: Response Time for GET Playlist Items Exceeds 200 ms

Summary:
The response time for retrieving playlist items using the GET request exceeds 200 ms, whereas it should be under 200 ms.

Preconditions:
- A PC with Google Chrome browser.
- A valid Spotify account.
- The Postman tool installed and opened.
- Proper authentication to access the Spotify API.
- A playlist with items to be retrieved.

Steps to Reproduce:

Send the following request:
curl --request GET \
  --url https://api.spotify.com/v1/playlists/{playlist_id}/tracks \
  --header 'Authorization: Bearer {refreshed_token}'

Expected Results:
The response time should be less than 200 ms.

Actual Results:
The response time consistently exceeds 200 ms.


Test Case 3: Response Time for GET Search for Item Exceeds 200 ms

Summary:
The response time for searching for an item using the GET request exceeds 200 ms, whereas it should be under 200 ms.

Preconditions:
- A PC with Google Chrome browser.
- A valid Spotify account.
- The Postman tool installed and opened.
- Proper authentication to access the Spotify API.

Steps to Reproduce:

Send the following request:
curl --request GET \
  --url 'https://api.spotify.com/v1/search?q=rock&type=track&limit=50' \
  --header 'Authorization: Bearer {refreshed_token}'

Expected Results:
The response time should be less than 200 ms.

Actual Results:
The response time consistently exceeds 200 ms.

<h2>Conclusions</h2>

During the testing phase, a total of 44 tests were created and executed, out of which 3 tests failed. Due to time constraints, the following functionalities were not tested: Albums, Audiobooks, Categories, Chapters, Episodes, Genres, Markets, Player, Shows, and Tracks.

Three bugs were identified during testing, categorized as 2 low-risk and 1 medium-risk issues. These bugs do not significantly impact the application, but it is recommended to prioritize fixing the medium-risk bug in the near future.


