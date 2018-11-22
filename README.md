public class TestDepartament {
    public static Departament__c createDepartament(String Name, Id officeId) {
       Departament__c departament = new Departament__c(
            Name = Name,
            Office__c = officeId
        ); 
        
        Database.SaveResult sv = Database.insert(Departament);
        
        return Departament;
      }
      
      public static Boolean deleteDepartament(Id officeId) {
        try {
            delete new Departament__c(Id = officeId);
        } catch(Exception ex) {
            return false;
        }
        
          return true;
      }
    
      public static Departament__c updateDepartament(Id officeId, String Name) {
          Departament__c departament = new Departament__c(
            Id = officeId,
            Name = Name
        );        
                
        Database.SaveResult sv = Database.update(Departament);
        
        return Departament;
      }
}
