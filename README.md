# React Native: Unhandled JS Exception: TypeError: Cannot read properties of null (reading 'someProperty')

This repository demonstrates a common error in React Native applications where a state variable is accessed before it has been initialized, leading to a `TypeError: Cannot read properties of null (reading 'someProperty')` exception.  The error arises from attempting to access properties of a state variable that is still `null` because an asynchronous operation to populate it hasn't completed yet.

## Problem

The issue occurs within a `useEffect` hook where an asynchronous operation (like a network request) fetches data to update the component's state. If the component attempts to render elements that rely on that data before the asynchronous operation is finished, the `null` value of the state variable leads to the error.

## Solution

The solution involves using conditional rendering to prevent accessing the state variable until it's been populated with data.  This is achieved by checking if the state is not null before attempting to access any of its properties.  Alternatively, you can display a loading indicator to inform the user while the data is being fetched.