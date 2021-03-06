# student_on_a_module_instance

* [STUDENT_ON_A_MODULE_INSTANCE_ID](#student_on_a_module_instance_id) **
* [STUDENT_COURSE_MEMBERSHIP_ID](student_course_membership.md#student_course_membership_id) [1] *
* [MOD_INSTANCE_ID](module_instance.md#mod_instance_id) [1] *
* [COURSE_INSTANCE_ID](course_instance.md#course_instance_id) [1]
* [STUDENT_ID](student.md#student_id) [1]
* [MOD_RESULT](#mod_result) [0..1]
* [MOD_RETAKE](#mod_retake) [0..1]
* [MOD_TRAILING](#mod_trailing) [0..1]
* [MOD_START_DATE](#mod_start_date) [0..1]
* [MOD_END_DATE](#mod_end_date) [0..1]
* [MOD_FIRST_MARK](#mod_first_mark) [0..1]
* [MOD_ACTUAL_MARK](#mod_actual_mark) [0..1]
* [MOD_AGREED_MARK](#mod_agreed_mark) [0..1]
* [MOD_RAW_ACTUAL_MARK](#mod_raw_actual_mark) [0..1]
* [MOD_RAW_AGREED_MARK](#mod_raw_agreed_mark) [0..1]
* [MOD_FIRST_GRADE](#mod_first_grade) [0..1]
* [MOD_ACTUAL_GRADE](#mod_actual_grade) [0..1]
* [MOD_AGREED_GRADE](#mod_agreed_grade) [0..1]
* [MOD_CREDITS_ACHIEVED](#mod_credits_achieved) [0..1]
* [MOD_CURRENT_ATTEMPT](#mod_current_attempt) [0..1]
* [MOD_COMPLETED_ATTEMPT](#mod_completed_attempt) [0..1]
* [X_MOD_NAME](#x_mod_name) [0..1]
* [MOD_ACADEMIC_YEAR](module_instance.md#mod_academic_year) [1]
* [MOD_OPTIONAL](#mod_optional) [0..1]
* [PROVIDED_AT](assessment_instance.md#provided_at) [0..1]

\** indicates that the property is the primary key for this entity; if not provided by data supplier, will be Learning Data Hub generated.   
\* indicates that the property is part of a uniqueness constraint for this entity.

API endpoint name: **studentmoduleinstance**

## Description of student_on_a_module_instance entity
A student_on_a_module_instance describes a student's performance on a specific module.

## Notes
This entity is similar to a HESA StudentOnModule element or a HEDIIP Module Instance entity.

## STUDENT_ON_A_MODULE_INSTANCE_ID
### Description
Primary key. Where not supplied by data provider, the primary key will be generated by the Learning Data Hub loading mechanism.

### Purpose
Enables easy reference to student_on_a_module_instance.

### Derivation
Jisc

### Format
String (255)

### Notes
Where not supplied by data provider, the primary key will be generated by the Learning Data Hub loading mechanism.

## MOD_RESULT
### Description
Indicates whether the student passed the module, didn't pass the module, deferred the module or whether this information is not known because the module hasn't been completed yet.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values

<table>
<tr><td>MOD_RESULT</td><td>DESCRIPTION(ENGLISH)</td><td>DESCRIPTION(WELSH)  </td></tr>
<tr><td>1</td><td>Pass</td><td>  </td></tr>
<tr><td>2</td><td>Fail</td><td>  </td></tr>
<tr><td>3</td><td>Not known</td><td> </td></tr>
</table>  

### Format
String (255)

### Notes
Code 3 is applied in all cases where the outcome is either not known (yet), or doesn't apply because the student hasn't been assessed yet. Omitting this property could impair the functionality of analytics applications such as student apps or dashboards.


## MOD_RETAKE
### Description
Whether this is a retake of the module for that student.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values

<table>
<tr><td>MOD_RETAKE</td><td>DESCRIPTION(ENGLISH)</td><td>DESCRIPTION(WELSH)  </td></tr>
<tr><td>1</td><td>Yes</td><td>Ie  </td></tr>
<tr><td>2</td><td>No</td><td>Na</td></tr>
</table>  

### Format
String (255)

### Notes

## MOD_TRAILING
### Description
Whether the student failed the module and is taking it again in the following academic year in addition to other modules, while continuing on the course.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
<table>
<tr><td>MOD_TRAILING</td><td>DESCRIPTION(ENGLISH)</td><td>DESCRIPTION(WELSH)</td></tr>
<tr><td>1</td><td>Yes</td><td>Ie</td></tr>
<tr><td>2</td><td>No</td><td>Na</td></tr>
</table>  

### Format
String (255)

### Notes
For a retake in the same academic year, use MOD_RETAKE, not this property. MOD_TRAILING is a sub-set of MOD_RETAKE; if MOD_TRAILING is set to "1", then MOD_RETAKE must also be set to "1". A re-take or re-sit (indicated by MOD_RETAKE) may happen in the same academic year as the original module instance. MOD_TRAILING only happens when the student takes the trailing module alongside continuing modules in the next academic year.
<<<<<<< HEAD

=======
>>>>>>> master

## MOD_START_DATE
### Description
Start date of this module_instance

### Purpose
Analytics and display

### Derivation
Jisc

### Valid Values
Date in ISO 8601 format - YYYY-MM-DD

### Format
String in ISO 8601 Date extended format - YYYY-MM-DD

### Notes
The start and end date of a module_instance MUST fall at or between the start and end date of a course_instance.
Omitting this property could impair the functionality of analytics applications such as student apps or dashboards.


## MOD_END_DATE
### Description
End date of this module_instance

### Purpose
Analytics and display

### Derivation
Jisc

### Valid Values
Date in ISO 8601 format - YYYY-MM-DD

### Format
String in ISO 8601 Date extended format - YYYY-MM-DD

### Notes
The start and end date of a module_instance MUST fall at or between the start and end date of a course_instance.
Omitting this property could impair the functionality of analytics applications such as student apps or dashboards.


## MOD_FIRST_MARK
### Description
The agreed mark a student was awarded on their first attempt at the module.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
0-100

### Format
Decimal

### Notes
The value represents a percentage; for example, a value of "63.75" means 63.75%, a value of "50" means 50%.
This mark should not be changed after subsequent attempts at the same module, as it is used in analytics.


## MOD_ACTUAL_MARK
### Description
The mark awarded to the learner as first recorded in the SRS, usually but not always, prior to formal moderation and exam board confirmation. The value of MOD_ACTUAL MARK is expressed as a percentage; for example, a value of "63.75" means 63.75%, a value of "50" means 50%.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
0-100

### Format
Decimal

### Notes
MOD_ACTUAL_MARK should only be part of a UDD compliant dataset if there is a moderation process and if the result of that process is available in the source data.


## MOD_AGREED_MARK
### Description
The mark recorded after any moderation or confirmation processes, or the only recorded mark if there are no moderation or confirmation processes. This mark is typically the one used to determine degree classification.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
0-100

### Format
Decimal

### Notes
The value represents a percentage; for example, a value of "63.75" means 63.75%, a value of "50" means 50%.
MOD_AGREED_MARK is expected to be present in any UDD compliant dataset as soon as it becomes available.

## MOD_RAW_ACTUAL_MARK
### Description
The original mark scored by the student.

### Purpose
Storage of the original numerical score.

### Derivation
Institution

### Valid Values
Any decimal value

### Format
Decimal

### Notes
Can contain any decimal value, for example "59", "162.87", and so on; this value may or may not be a percentage. MOD_ACTUAL_MARK contains a representation of MOD_RAW_ACTUAL_MARK explicitly as a percentage.


## MOD_RAW_AGREED_MARK
### Description
The mark scored by the student after any moderation or confirmation processes, or the only recorded mark if there are no moderation or confirmation processes.

### Purpose
Storage of the confirmed numerical score.

### Derivation
Institution

### Valid Values
Any decimal value

### Format
Decimal

### Notes
Can contain any decimal value, for example "59", "162.87", and so on; this value may or may not be a percentage. MOD_AGREED_MARK contains a representation of MOD_RAW_AGREED_MARK explicitly as a percentage.


## MOD_RAW_ACTUAL_MARK
### Description
The original mark scored by the student.

### Purpose
Storage of the original numerical score.

### Derivation
Institution

### Valid Values
Any decimal value

### Format
Decimal

### Notes
Can contain any decimal value, for example "59", "162.87", and so on; this value may or may not be a percentage. MOD_ACTUAL_MARK contains a representation of MOD_RAW_ACTUAL_MARK explicitly as a percentage.


## MOD_RAW_AGREED_MARK
### Description
The mark scored by the student after any moderation or confirmation processes, or the only recorded mark if there are no moderation or confirmation processes.

### Purpose
Storage of the confirmed numerical score.

### Derivation
Institution

### Valid Values
Any decimal value

### Format
Decimal

### Notes
Can contain any decimal value, for example "59", "162.87", and so on; this value may or may not be a percentage. MOD_AGREED_MARK contains a representation of MOD_RAW_AGREED_MARK explicitly as a percentage.


## MOD_FIRST_GRADE
### Description
The agreed grade a student was awarded on their first attempt at the module.

### Purpose
Analytics. The first grade a student receives on the module is used to help monitor what changes to marks are made during the re-assessment process.

### Derivation
Jisc

### Valid Values
Any

### Format
String (255)

### Notes
This grade should not be changed after subsequent attempts at the same module, as it is used in analytics.


## MOD_ACTUAL_GRADE
### Description
The grade awarded to the learner as first recorded in the SRS, usually but not always, prior to formal moderation and exam board confirmation.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
Any

### Format
String (255)

### Notes
MOD_ACTUAL_GRADE should only be part of a UDD compliant dataset if there is a moderation process and if the result of that process is available in the source data.


## MOD_AGREED_GRADE
### Description
The grade recorded after any moderation or confirmation processes, or the only recorded grade if there are no moderation or confirmation processes. This grade is typically the one used to determine degree classification.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
Any

### Format
String (255)

### Notes
MOD_AGREED_GRADE is expected to be present in any UDD compliant dataset as soon as it becomes available.

## MOD_CREDITS_ACHIEVED
### Description
The number of credits awarded for the module.

### Purpose
Analytics

### Derivation
https://www.hesa.ac.uk/collection/c18051/a/crdtpts

### Valid Values
Any

### Format
Int

### Notes


## MOD_CURRENT_ATTEMPT
### Description
The number of times so far that a student has taken a module_instance, whether assessed or not. For example: regardless of assessment or result, for the 1st attempt the value would be '1'; a non-assessed 2nd attempt with no recorded result would have a value of '2'; and a 3rd attempt with an agreed result would have a value of '3'.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
Non-zero, positive integer

### Format
Int

### Notes
If the student has made no attempts, leave out this property; do not supply a value of "0".

Omitting this property may hinder the development or use of an effective analytics model.

## MOD_COMPLETED_ATTEMPT
### Description
The number of assessed attempts taken by a student to complete a module_instance. For example: if a student completes a module_instance at the 2nd assessed attempt with an agreed result, the MOD_COMPLETED_ATTEMPT property would have a value of '2', even if MOD_CURRENT_ATTEMPT has a value of '3', owing to a non-assessed 2nd attempt.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values
Non-zero, positive integer

### Format
Int

### Notes
If the student has made no attempts, leave out this property; do not supply a value of "0".

## X_MOD_NAME
### Description
An extra implementation optimisation that isn't part of the UDD model. Its value is identical to that of the relevant module.MOD_NAME.

### Purpose
Implementation optimisation

### Derivation
Jisc; module.MOD_NAME

### Valid Values
Any

### Format
String (255)

### Notes
This data is generated internally from existing data, and does not need to be supplied by an institution.

## MOD_OPTIONAL
### Description
Whether or not this student_on_a_module_instance relates to an optional module.

### Purpose
Analytics

### Derivation
Jisc

### Valid Values

<table>
<tr><td>MOD_OPTIONAL</td><td>DESCRIPTION(ENGLISH)</td><td>DESCRIPTION(WELSH)  </td></tr>
<tr><td>1</td><td>Yes</td><td>Ie  </td></tr>
<tr><td>2</td><td>No</td><td>Na</td></tr>
</table>  

### Format
String (255)

### Notes
