# General Guidance
## Example: An information system that is used by people, requiring the creation and tracking of data via software and supporting key processes within the organisation.

The requirements for the project are that it is used by people, requiring the creation and tracking of data via software and supporting key processes within the organisation.

The stakeholders are key users of the system. They represent why the system exists and the system allows them to carry out their tasks, informing them of business process events, successes and failures. Each stakeholder should play a separate role in the system from the other stakeholders. There may be several users who do the same thing but the role is the important aspect and that stakeholder type will be the one who is identified, rather than all users who hold that role in the system. Developers are generally not stakeholders as they will not use the completed system. They only implement the requirements.

## Further details
It should consider the business events that trigger business processes to act on the data. How does the data represent the business, how is it structured and who needs to access it and when? Each business event triggers a corresponding business process. Who needs to know a particular business process has been initiated and who needs to know when it has completed? Does anyone need to know if the process fails? If so, how does the system manage alerts to key stakeholders?

**Questions to consider when scoping such a system that revolves around information and data:**
How does the data represent the business, how is it structured and who needs to access it and when? Each business event triggers a corresponding business process. Who needs to know a particular business process has been initiated and who needs to know when it has completed? Does anyone need to know if the process fails? If so, how does the system manage alerts to key stakeholders?

How the data is tracked through the system to allow stakeholders to engage with the business processes? Does anyone need to know when a project is created/completed etc? Are there stages in a project? Do stakeholders need to know when a project moves between stages? Can projects be late or overdue? Are notifications sent to key stakeholders in these cases?

## Further general guidance
It is advised to scope the problem for an appropriate size: have it broad enough for make it worth the infrastructural resources it takes for creating, then later maintaining it; have it not too broad so it is of a managable size.

---

# Example
**Organisation:**
Tranquil Records, based in Hungary, a record label company that produces, promotes and markets recorded music and corresponding videos, recruits and develops new artists, publishes their music, enforces copyrights and collects royalties. The record label focuses on artists in the field of electronic and experimental music. It hires master engineers, music producers, event professionals and advertisers to support artists' work, development and exposure to the public.

**Problem:**
Tranquil Records needs a content management system to streamline key processes in music production: the recording, producing, mastering, copyrighting and promoting pieces of music and albums. The system should allow the creation of various digital artefacts (e.g. raw recordings, stems, mastered stems and projects, legal items such as contracts and licenses, artworks). These artefacts are the products of distinct processes, and some processes depend on others. The system should allow handing over certain artefacts to certain processes, and these processes should lead to completed single pieces of music or albums, ready for releasing.  

**Key business processes:**
- Songwriting and Composition
- Tracking (includes composing, recording and arranging)
- Editing
- Mixing
- Mastering
- Artwork
- Legal 
- Publishing

**Key stakeholders and roles:**
- Songwriters
- Musical artists
- Producers
- Mastering engineers
- Graphic designers
- Music attorneys (entertainment lawyers)
- Publishing team


**Are there stages in a project? Do stakeholders need to know when a project moves between stages?**
There are 2 types of project:
- Song
- Release

**A song** is a single piece of music (a song or an instrumental/ambient piece). It has the following processes which are also considered to be stages of development:

| Stage order | Stage | Inputs and artefacts | Users | Stakeholders |
| - | - | - | - | - |
| 1. | Songwriting and Composition | **Inputs:** None.<br /> **Artefacts:** A text file containing a description of the concept of the piece of music from an artistic point of view, and a finalized high level idea of what sections it should have and in what order. Also, if it is not an instrumental or ambient piece, another text file containing the lyrics. | <li>Songwriters <li>Musical artists | <li>Producers <li>Graphic artists | 
| 2. | Tracking (includes composing, recording and arranging) | **Inputs:** Artefacts from Songwriting and Composition. <br />**Artefacts:** A digital Audio Workstation (DAW) project file, raw recordings. | <li>Musical artists <li>Producers | Producers | 
| 3. | Editing | **Inputs:** Artefacts from Tracking. <br/> **Artefacts:** A DAW project file, stem tracks in .WAV format.  | Producers | Producers |
| 4. | Mixing | **Inputs:** Artefacts from Editing. <br/> **Artefacts:** A DAW project file, stem tracks in .WAV format. | Producers | Mastering Engineers | 
| 5. | Mastering | **Inputs:** Artefacts from Editing. <br/> **Artefacts:** A DAW project file, mastered stem tracks in .WAV format, compiled music files in .MP3, .WAV and .FLAC format | Mastering Engineers | <li>Publishing team <li>Producers <li>Musical artists <li>Songwriters |

**A stage (or process) can have the following states:**
	- Pending (has not been started yet)
	- In progress (has been started)
	- Completed
	- Revision required (refinement requested at a follow-up stage: _e.g. arrangement concieved to be "boring" at tracking stage, or mixing is too surgical or barely noticable at mastering stage_ )
	
Each stage's stakeholder(s) need(s) to be notified when previous stage's state changes (e.g. via email). 


**A release** consists of either a _single_ or a _collection_ of finished **songs**.
There are no stages in a **release** project, but there are processes, which are either partially or completely independent of each other:

| Process | Dependency | Artefacts | Users | Stakeholders |
| -| - | - | - | - |
| Artwork | This process does not depend on other processes. | Digital images. | Graphic artists | <li>Music attorneys <li>Publishing team |
| Legal | This process can be started without dependency of other processes, but can only be finished when all **song** projects contained in this **release** project are completed, and all other **release** processes are completed. | Legal documents such as contracts and copyrights | Music attorneys | Publishing team |
| Publishing | This process depends on legal process. | Digital copies of released album/EP/single | Publishing team | All other stakeholders associated with any of the project's other processes |

		

**How does the data represent the business, how is it structured and who needs to access it and when?**
Each individual process yields an artefact which will be different types of data, stored perhaps as a compressed file.


**How the data is tracked through the system to allow stakeholders to engage with the business processes?**
Artefacts of different processes are stored by a file storage solution.
When a process' corresponding atrefact is either created or modified, stakeholders of that process should be notified (perhaps via email), so they can take action accordingly (e.g. to initiate a follow-up process, or to update a legal document).


**Each business event triggers a corresponding business process. Who needs to know a particular business process has been initiated and who needs to know when it has completed?**
Publishing team should be notified about the initiation and all other state changes of a process.
Stakeholders of each processes should be notified about the completion of that particular process.


**Does anyone need to know if the process fails? If so, how does the system manage alerts to key stakeholders?**
Yes.
When uploading an artefact to system's file storage at the end of a business process, the system should recognise if the operation failes, and should notify the user immediately to try again.


**Does anyone need to know when a project is created/completed etc?**
Yes. Users with different roles are associated to projects at creation.
All users of a single business process are also a stakeholder of at least one other business process.
All stakeholders of a project should be notified when a project is completed. 


	

**Can projects be late or overdue? Are notifications sent to key stakeholders in these cases?**
No. There are no deadlines defined for the completion of projects or their business processes.
	

