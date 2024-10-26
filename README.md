# **Music-Metadata-and-Lyrics**
Python project that updates metadata (including album art) and searches for lyrics from the Genius API. This is a very quick and easy way to get the metadata updated, however it will only this for 1 song at a time. 

Full creting goes to the original, Fingolfin 7: https://github.com/Fingolfin7 & Fer-hnndz https://github.com/fer-hnndz, I came across this when looking to try and update some meta from a usefull source and after testing several others this seem to be the most straightforward however there where some issues with the versions used, and the requirements.txt file. 

I am completly new to python scripting, so do not know if what I did with the requirements.txt file would have had some serious implications but after alot of pip install -r requirements.txt and pip uninstall -r requirements.txt I managed to get it working with no issues and running in the current latest Python: 3.12.6 (Windows 10 x64)

**## Changes to requirements.txt**
* Reading up on all the requirements in the requirements.txt, and seeing if they are required to be ran on specified version
* Reviewed all the scripts within /<your_saved_clone_project>source/ if there where links to specific dependencies within the versions in requirements.txt
* requirements.txt
  ```
  **OG requirements.txt**      |  **requirements.txt**  
  ---------------------------------------------
  | unidecode==1.2.0       |  unidecode       |
  | beautifulsoup4==4.9.3  |  beautifulsoup4  |
  | coverage==5.5          |  coverage        |
  | deprecation==2.1.0     |  deprecation     |
  | eyed3==0.9.6           |  eyed3           |
  | filetype==1.0.7        |  filetype        |
  | packaging==21.0        |  packaging       |
  | pyparsing==2.4.7       |  pyparsing       |
  | soupsieve==2.2.1       |  soupsieve       |
  | toml==0.10.2           |  toml            |
  | pillow==8.3.1          |  pillow          |
  | requests==2.26.0       |  request         |
  ---------------------------------------------
```
```


## **Requirements**
* A [Genius API Token](https://docs.genius.com/#/getting-started-h1)

## **Genius API Token**
* Give you App a name. Called it what ever you want.
* URL for your App Website URL, simply use 
  * App Website URL
  * http://local.host

## **Update your auth_token.txt**
* Login to https://genius.com/api-clients
* Copy your "Client Access Tokken" 
* Create auth_token.txt file within /<your_saved_clone_project>source/
* Paste your: "Client Access Token"
* Save the file auth_tokken.txt & confirm you saved it in /<your_saved_clone_project>source/
* In your terminal:
  * Navigate to cd /<your_saved_clone_project>source/
  * Verify that your tokken has been added to auth_tokken:

    ```bash
    py get_auth_token.py
    ```
    
  * If added correctly, there will be no errors that read:
    ```bash
    'Empty file. Please fill it in with Genius token.'
    ```
* Now you are ready, to update a track.
    
## **Getting the project**

Download the project as a ZIP (extract to a location where you save all your projects or will run this script from) or clone it with git desktop app for windows. 

## **Virtual environment:**

* Create a virtual environment, I recommend this especially if you are new to this stuff like me, and broken other environment variables :) not fun trying to fix something else that you where doing. 

* It is really simple:
  * 1: Navigate to you cloned project. (via terminal: cd /<your_saved_clone_project>/)
  * 2: in terminal type where name is call it what you want your virtual env to be called. 
```bash
    py -m venv name
```
  * 3: Start the virtual environment

```bash
<your_saved_clone_project>/scripts/activate
```
  * 4: Now everything you install will be installed in your virtual environment. This will ensure you do not break anything else.
  * 5: When finished it is simple to get out of the virtual environment.

```bash
deactivate
```

  * **REMEMBER:** Always start your virtual environment when you are running this, otherwise nothing will work  

### Install the requisites by running

```bash
pip install -r requirements.txt
```

You will need to create an `auth_token.txt` file in the `Source` folder and paste a Genius token inside it. 
You can generate a genius token [here](https://docs.genius.com/#/getting-started-h1)

## Update Metadata
`Metadata.py` takes in an mp3 file (or a folder path) and searches for the corresponding metadata from Genius.com using the Genius API and Eyed3 module.

__Here is an example in a test folder I made:__

![image](https://user-images.githubusercontent.com/63872314/128647612-7f2d8515-69ad-4739-b986-fe6ce9ef14d1.png)

__Run Metadata Search (collected from Genius.com):__

![image](https://user-images.githubusercontent.com/63872314/128647830-2b3e475a-8fe5-41d5-9aa5-fe424e63d00e.png)

__Finished Search:__

![image](https://user-images.githubusercontent.com/63872314/128647739-e025fb6e-d320-4e5d-88e7-4eb40c8e175e.png)

__Updated mp3 file:__

![image](https://user-images.githubusercontent.com/63872314/128647768-c0492c67-567c-4e8a-b6b5-4eba72a060f9.png)

Metadata.py contains the funtcion get_metadata,

```python
get_metadata(song_file, art_option=0)
```

Which is called with a file path to an mp3 file, and an optional `art_option` which is set to 0 by default.

Setting `art_option` to 0 will update the file with the songs *Album Art*,

Setting it to 1 will update the file to the songs *Song Art*, which sometimes differ.

## Search Song Lyrics
`GeniusLyrics.py` takes in a song name and artist name and searches Genius.com for the lyrics. The lyrics are saved to a json file called `song_lyrics.json`. Searches are performed on this saved data when offline. Here is an example, running `GUI.py` which is a simple gui for getting song lyrics

__Example Search__:

![image](https://user-images.githubusercontent.com/63872314/128579595-604eba7a-b5f2-4a3b-936d-5d20945767e9.png)

__Output__:

![image](https://user-images.githubusercontent.com/63872314/128579639-bb099cbe-0d5d-4a0f-99af-fe760f9c8308.png)

## Contribute to the project
Take a look, run the code, and contribute if you'd like!






