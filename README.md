# Spotify_ETL_using_AWS
This is main repo where all my Data Engineering Projects are located. Feel free to give it shot on your own. Below are list of access, tools and ERD diagram(Attached seaprately) you can refer to understsnd the project the, follow the steps: 


Tools and access you need :

1. Jupyter Notebook: For this, I suggest download software called anaconda and use Notebook avaialble in it linked here : https://www.anaconda.com/download
2. Spotify Developer Acct: To get Client_Id and Client_Secret so, you can use Spotify API to get the data you need. Link: https://developer.spotify.com/dashboard
3. AWS Account: You can get it for free if you have not used AWS services before. Start here :https://aws.amazon.com/free/?gclid=Cj0KCQjwq86wBhDiARIsAJhuphmKFtXFc9USYaf36Ipj2Ct5MEEjm8TGWBczO-PRqe-OfkwT2cbDF0MaAhgjEALw_wcB&trk=7541ebd3-552d-4f98-9357-b542436aa66c&sc_channel=ps&ef_id=Cj0KCQjwq86wBhDiARIsAJhuphmKFtXFc9USYaf36Ipj2Ct5MEEjm8TGWBczO-PRqe-OfkwT2cbDF0MaAhgjEALw_wcB:G:s&s_kwcid=AL!4422!3!651751058790!e!!g!!aws%20account!19852662149!145019243897&all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all


Steps:
1. create a spotify developer acct to get client id and secret id.
2. After downloading Anaconda and launching Notebook, open a new ".py" file. Follow the codes in "Notebook" folder. Make sure you type everything I have there so, you actaully understand it.
3. After you run the code sucessfully in notebook with no errors its time to move on to AWS and do this in AWS.
4. Create, AWS account. Open S3 and create a bucket in any region that is close to you.
5. In that bucket create 1 folder named "Spotify_ETL_Project" and inside "Spotify_ETL_Project" folder create two sub folders called "raw" and "transformed"
6. In "raw" folder, create two sub folders named "to_be_be process" and "alreay_processed"
7. In "transformed" folder, create 3 sub-folders named "album_data", "artist_data" and "songs_data"
8. Duplicate the AWS tab in your browers and aws search ( top right); type "Lambda" and search for it.
9. Click on "Create Function" in lambda.
10. Make sure to give "Administrator Access" to your 2 lamda fn so, you dont have to face any connection issue. Google "How to give Admin Access to Lamda fn" and follow the steps.
11. Name the 1st lambda fn as "spotify_api_data_extract_fn" and 2nd one as "spotify_transformation_load_fn" for SIMPLICITY.
12. Open the 1st lamda fn "spotify_api_data_extract_fn" and refer back to "spotify_api_data_extract_fn.zip" code and test if you are seeeing the data in s3 buket under "raw/to_be_transformed". If no, please checkl the code properly.
13. Open the 2nd lambda fn "spotify_transformation_load_fn" and follow the steps and this should give you data in processed folders under "artist_data", "album_data" and "songs_data"

IF YOU DID THIS SUCESSFULLY, YOU HAVE JUST COMPLETED 90% OF THE TASK.

14. Add trigger in your 1st lamda fn and it should be called "Event_bridge_cloud watcg....". Make sure to set time interval at 1 min to quickly test our use case of data extraction.
15. Once you have data in tranformed folder, we will create a crawler to read data from 3 sub folder in transformed folders.

16. Google "how to add crawler on folder in S3". I will soon upload video to walk through it but for now, follow any other person's video you like.
17. After this you can query the data using Athena and use it for multiple analytical projects.
    
