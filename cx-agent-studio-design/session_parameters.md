# Session Parameters

- **phone_number**  
  Stores the registered mobile number provided by the customer.

- **dob**  
  Stores the customer's date of birth used during authentication.

- **verification_answer_1**  
  Stores the response to the first verification question.

- **verification_answer_2**  
  Stores the response to the second verification question.

- **auth_status**  
  Stores the authentication result (Authenticated / Not Authenticated).

- **retry_count**  
  Tracks the number of authentication retry attempts made by the customer.

- **customer_id**  
  Stores the unique customer identifier retrieved after successful authentication.

- **customer_name**  
  Stores the authenticated customer's name.

- **policy_list**  
  Stores all insurance policies associated with the authenticated customer.

- **selected_policy_id**  
  Stores the policy selected by the customer for further actions.

- **claim_list**  
  Stores all claims associated with the selected policy.

- **selected_claim_id**  
  Stores the claim selected by the customer.

- **product_type**  
  Stores the insurance product selected during New User Onboarding (Motor, Health, Life, etc.).

- **vehicle_number**  
  Stores the vehicle registration number provided during Motor Insurance onboarding.

- **chassis_number**  
  Stores the chassis number used for vehicle verification.

- **request_type**  
  Stores the type of customer update request (DOB, Mobile Number,etc.).

- **request_id**  
  Stores the unique request ID generated after submitting an update request.

- **new_value**  
  Stores the new information submitted by the customer for the update request.

- **escalation_reason**  
  Stores the customer's reason for requesting human assistance.

- **ticket_id**  
  Stores the support ticket number generated during agent escalation.

- **conversation_summary**  
  Stores a summary of the conversation that will be transferred to the live support agent during handoff.
