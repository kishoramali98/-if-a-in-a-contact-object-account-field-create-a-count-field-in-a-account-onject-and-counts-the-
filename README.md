# -if-a-in-a-contact-object-account-field-create-a-count-field-in-a-account-onject-and-counts-the-
 //if a  in a contact object account field create a count field  in a account onject and counts the contacts
public class contactHandler 
{
      public static void afterInserthandler(list<contact> newcon)
       {
        set<id>accountids=new set<id>();//this set for set of ids
          for(contact con:newcon)  // here i am going to check the contact id or not
          {
              if(string.isNotBlank(con.AccountId))  // if my accountName is blank then
              {
                 //i am going to get this account id(AccountId)from this contact (con)            
                   accountids.add(con.AccountId);  //to store all account ids in set
                  
                   
/*   list<aggregateResult>res=[select AccountId ,count(id)totalscontact from contact //retrive the ids who is active contacts 
                                            where active__c = true and AccountId 
                                            IN:accountids group By AccountId];
                  
                  list<account> accountstoupdate=new list<account>();//list for updated ids
                  
                  for(aggregateResult resumes : res)
                  {
                      //get acccount id and number of active cont
                        // now we have to get account id using simply get method
                    string aaccc= string.valueof(resumes.get('AccountId'));//aplyala tya aggroigate madhun account id  ghyachyay eka varable madhye ani string convert
                      integer totalscon=integer.valueOf(resumes.get('totalscontact'));//count id ghyala ailyas dilay quary madhye  ani te integer mahye ghetlay
                      account acc= new account(id=aaccc,Active_Contacts__c = totalscon);//here we update id and active contact field update 
                      accountstoupdate.add(acc);
                  }
                  update accountstoupdate;
*/
