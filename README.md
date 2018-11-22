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

public class TestOffice {
    public static Office__c createOffice(String Name) {
        Office__c office = new Office__c(
            Name = Name
        );        
                
        Database.SaveResult sv = Database.insert(Office);
        
        return Office;
      }
      
      public static Boolean deleteOffice(Id officeId) {
        try {
            delete new Office__c(Id = officeId);
        } catch(Exception ex) {
            return false;
        }
        
          return true;
      }
    
      public static Office__c updateOffice(Id officeId, String Name) {
          Office__c office = new Office__c(
            Id = officeId,
            Name = Name
        );        
                
        Database.SaveResult sv = Database.update(Office);
        
        return Office;
      }
}

public class TestCrud {
    public static employee__c createEmployee(String lastName, Id departamentId) {
        employee__c employee = new employee__c(
            Name = lastName,
            Departaments__c = departamentId
        );        
                
        Database.SaveResult sv = Database.insert(employee);
        
        return employee;
      }
      
      public static Boolean deleteEmployee(Id employeeId) {
        try {
            delete new employee__c(Id = employeeId);
        } catch(Exception ex) {
            return false;
        }
        
          return true;
      }
    
      public static employee__c updateEmployee(Id employeeId, String lastName) {
          employee__c employee = new employee__c(
            Id = employeeId,
            Name = lastName
        );        
                
        Database.SaveResult sv = Database.update(employee);
        
        return employee;
      }
}
