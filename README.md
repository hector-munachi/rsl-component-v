# rsl-component-v

A reusable Vue 3 component that simplifies the process of adding Region, State, and LGA selection drop-downs to forms in web applications. This helps developers by eliminating the need to build these inputs from scratch. 

🔗 **[Demo](https://rsl-component-v.netlify.app/)**

## Installation

Install this package with npm or yarn:

```bash
# If you use npm:
npm install rsl-component-v

# Or if you use Yarn:
yarn add rsl-component-v
```
    
## Usage

Import and use the `InputRSLv` component in your Vue component.
```javascript
<template>
  <InputRSLV />
</template>

<script>
import InputRSLV from 'rsl-component-v';

export default {
  components: {
    InputRSLV,
  },
};
</script>

```

## Example


Here's an example of how you can use the `InputRSLV` component in a form:

```javascript
<template>
  <form>
    <InputSRLV v-model:selected-state="selectedState" v-model:selected-lga="selectedLga" />

    <!-- ... other form fields ... -->

    <button @click.prevent="submitForm">Submit</button>
  </form>
</template>

<script>
import { ref } from 'vue';
import InputRSLV from 'rsl-component-v';

export default {
  components: { InputSRLV },
  setup() {
    const selectedState = ref('');
    const selectedLga = ref('');

    const submitForm = () => {
      // Do something with the captured values, such as sending them to a server
      console.log(selectedState.value, selectedLga.value, InputSRLV.region.value);
    };

    return { selectedState, selectedLga, submitForm };
  }
};
</script>

```
In this example, we passed the `selectedState` and `selectedLga` variables to the `InputSRLV` component using `v-model`. These variables will be updated when the user selects a state and an LGA.

To capture the value of the region input, we accessed the region computed property of the `InputSRLV` component using `InputSRLV.region.value`.

Finally, we defined a `submitForm` function that logs the captured values to the console. You can replace this function with your own logic for handling the form submission.


## Contributing

We welcome and appreciate contributions from the community to help improve the codebase and make it even better and simpler! Whether it's fixing bugs, adding new features, improving documentation, or enhancing performance, your contributions can make a significant impact on the project.

<!-- See `here` for ways to get started.

Please adhere to this project's `code of conduct`. -->


## Acknowledgements

`InputRSLV` component was built with Vite and Vue 3. It uses pre-defined data for regions, states, and LGAs in Nigeria. The original code was provided by the user.
## Spread the word

If you find our npm package useful, please help us spread the word! Share it with your colleagues, friends, and the wider community. This can help us attract more contributors and improve the project's visibility.

We appreciate your contributions in making our npm package better and simpler! Thank you for your support.


## License

This project is licensed under the [MIT](https://choosealicense.com/licenses/mit/) License. 

