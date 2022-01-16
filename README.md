## Steps to learn formik tutorial

### Created a normal form with 3 fieds

- Name, Email and Channel
- For each field I had label and input field

### Installed formik and got useFormikContext

- useFormik accepts initialValues object
- these values are the starting values of form

### Set initial values

- In useFormik hook, we set initial values of form
- this is an object holding key-value pairs
- keys should be the name prop of input fields - name, email and channel in this case

### Make Formik track our field values

- Step 1 is to add initialValues (previous step)
- Step 2 is to add onChange and the value prop on the input fields
- Now the formik will track the form changes. To see form values, use formik.values

### Take a look yourself - Form values

- Added a console log statement to view the formik values
- See how the values change on typing in the form
- formik.values is the current form values at any time (updated form)
- TILL NOW WE HAVE LEARNT HOW TO MANAGE THE FORM FIELD AND UPDATE THE FORM. NOW LETS SEE HOW TO SUBMIT THE FORM

### Submit the form

- 2 steps: 1. specify onSubmit={formik.handleSubmit} handler on form tag
- Step 2. Specify onSubmit prop on formik context. This is a function that gets value param which is formik.values
- When we submit the form, this onSubmit method (in useFormikContext) is executed
- For submit button, add type='submit' to avoid any warnings
- TIME TO LEARN FORM VALIDATION

### Validate the form

- We need to add 2 rules ( 1. All fields are Required. 2. Email must be valid)
- to the formik, we specify thrid property 'validate' just like initialValues and onSubmit
- this 'validate' is also a method like onSubmit that recieves values as args
- this is a function/method will have to satisfy some conditions for the formik to work

  #### Conditions

  - 1.  The validate function must return an object. Let's create an object and return it. Let's call that object 'errors'
  - 2.  The keys of this errors object must be same as the keys of values object
        We have - values.name, values.email and values.channel
        So we must have - errors.name, errors.email and errors.channel
  - 3.  the values of each field must be a string specifying the error itself of that field

- Refactored the formik values by moving the formik object values on top level of code. This is just for readability
