# `useChangeSubject`

A hook that starts a transaction with the global dataset, then provides you with tools for modifying and committing that transaction given a specific subject.

Use this hook for forms.

```typescript
import { useChangeSubject, useResource } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./_ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const resource = useResource("https://example.com/card");
  const [profile, setProfile, commitProfile] = useChangeSubject(
    ProfileShapeType,
    "https://example.com/card#me"
  );

  const handleSubmit = async (e: React.FormEvent) => {
    e.preventDefault();
    const result = await commitProfile();
    if (result.isError) {
      console.error("Failed to update profile:", result.message);
    } else {
      console.log("Profile updated successfully!");
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input 
        type="text" 
        value={profile?.fn || ""} 
        onChange={(e) => {
          setProfile(resource, (cProfile) => {
            cProfile.fn = e.target.value;
          });
        }} 
      />
      <input type="submit" />
    </form>
  );
};
```

## Parameters

 - `shapeType: ShapeType` - The shape type of the subject
 - `subject: string | SubjectNode` - The URI of the subject
 - `options?: UseSubjectOptions` - Optional configuration

## Returns

Returns a tuple containing three elements:

1. **`subject`** - A linked data object for the specified subject, derived from a transaction dataset

2. **`setSubject`** - A function for modifying the subject. It takes two parameters:
   - `resource`: A resource object (typically from `useResource`) that contains the subject to modify
   - `changer`: A callback function that receives the subject and allows you to modify it

   ```typescript
   setSubject(resource, (subject) => {
     subject.property = "new value";
   });
   ```

3. **`commitSubject`** - An async function that commits all changes from the transaction dataset to the global dataset and remote dataset (if connected). Returns a Promise that resolves when the commit is successful or rejects if there's an error.