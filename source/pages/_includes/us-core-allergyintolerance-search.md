
- See the [General Guidance] section for additional rules and expectations when a server requires status parameters.
- See the [General Guidance] section for additional guidance on searching for multiple patients.

#### Mandatory Search Parameters:

The following search parameters, search parameter combinations SHALL be supported.  Any listed search parameter [modifiers], [comparators], [chains] and [composites] SHALL also be supported UNLESS they are listed as "optional" in which case they SHOULD be supported.:

1. **SHALL** support searching for all allergies for a patient using the **[`patient`](SearchParameter-us-core-allergyintolerance-patient.html)** search parameter:

    `GET [base]/AllergyIntolerance?patient=[reference]`

    Example:

      1. GET [base]/AllergyIntolerance?patient=1137192

    *Implementation Notes:* Fetches a bundle of all AllergyIntolerance resources for the specified patient ([how to search by reference])


#### Optional Search Parameters:

The following search parameters, search parameter combinations and search parameter [modifiers], [comparators], [chains] and [composites] SHOULD be supported.

1. **SHOULD** support searching using the combination of the **[`patient`](SearchParameter-us-core-allergyintolerance-patient.html)** and **[`clinical-status`](SearchParameter-us-core-allergyintolerance-clinical-status.html)** search parameters:

    `GET [base]/AllergyIntolerance?patient=[reference]&clinical-status={[system]}|[code]`

    Example:
    
      1. GET [base]/AllergyIntolerance?patient=[id]&amp;clinical-status=http://terminology.hl7.org/CodeSystem/allergyintolerance-clinical\|active

    *Implementation Notes:* Fetches a bundle of all AllergyIntolerance resources for the specified patient and status code.  This will not return any &#34;entered in error&#34; resources because of the conditional presence of the clinicalStatus element. ([how to search by reference] and [how to search by token])

{% include link-list.md %}
