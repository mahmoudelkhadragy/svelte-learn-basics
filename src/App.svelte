<script>
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import Header from "./UI/Header.svelte";
  import TextInput from "./UI/TextInput.svelte";

  let title = '';
  let subtitle = '';
  let description = '';
  let imageUrl = '';
  let address = '';
  let email = '';

  let meetups = [
    {
    id: 1,
    title: 'React Meetup',
    subtitle: 'A meetup for React enthusiasts',
    description: 'Join us to learn more about React and its ecosystem',
    imageUrl: 'https://via.placeholder.com/1000x450',
    address: '123 Main St, Anytown USA',
    contactEmail: 'reactmeetup@example.com'
  },
  {
    id: 2,
    title: 'Angular Meetup',
    subtitle: 'A meetup for Angular enthusiasts',
    description: 'Join us to learn more about Angular and its ecosystem',
    imageUrl: 'https://via.placeholder.com/1000x450',
    address: '456 Oak St, Anytown USA',
    contactEmail: 'angularmeetup@example.com'
  },
  {
    id: 3,
    title: 'Vue Meetup',
    subtitle: 'A meetup for Vue enthusiasts',
    description: 'Join us to learn more about Vue and its ecosystem',
    imageUrl: 'https://via.placeholder.com/1000x450',
    address: '789 Elm St, Anytown USA',
    contactEmail: 'vuemeetup@example.com'
  },
  {
    id: 4,
    title: 'Node.js Meetup',
    subtitle: 'A meetup for Node.js enthusiasts',
    description: 'Join us to learn more about Node.js and its ecosystem',
    imageUrl: 'https://via.placeholder.com/1000x450',
    address: '321 Pine St, Anytown USA',
    contactEmail: 'nodejsmeetup@example.com'
  },
  {
    id: 5,
    title: 'Python Meetup',
    subtitle: 'A meetup for Python enthusiasts',
    description: 'Join us to learn more about Python and its ecosystem',
    imageUrl: 'https://via.placeholder.com/1000x450',
    address: '654 Cedar St, Anytown USA',
    contactEmail: 'pythonmeetup@example.com'
  }
];

function addMeetup(){
  const newMeetup = {
    id: Math.random().toString(),
    contactEmail: email,
    title,
    subtitle,
    description,
    imageUrl,
    address
  }

  meetups = [newMeetup, ...meetups]
}

</script>
<style>
  main{
    margin-top: 5rem;
  }
  form{
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>
<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
    <TextInput
      label="Title" 
      id="title"
      value={title}
      on:input={event => title = event.target.value}
    />
    <TextInput
      label="Subtitle" 
      id="subtitle"
      value={subtitle}
      on:input={event => subtitle = event.target.value}
    />
    <TextInput
      label="ImageUrl" 
      id="imageUrl"
      value={imageUrl}
      on:input={event => imageUrl = event.target.value}
    />
    <TextInput
      label="Address" 
      id="address"
      value={address}
      on:input={event => address = event.target.value}
    />
    <TextInput
      label="Email" 
      id="email"
      value={email}
      controlType ='email'
      on:input={event => email = event.target.value}
    />
    <TextInput
      label="description" 
      id="description"
      value={description}
      controlType ='textarea'
      on:input={event => description = event.target.value}
    />
    <button>Add Meetup</button>
  </form>
</main>

<MeetupGrid {meetups} />