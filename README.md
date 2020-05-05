# Statment_Trigger
Create a statement trigger


trigger Statement_Trigger on Statement__c (after insert,after update) {
  
    if(trigger.isAfter && trigger.isInsert || trigger.isUpdate)
    {
        Rollup_Methods.rollupStatementsToRentalAgreement(trigger.new);
    }
}

