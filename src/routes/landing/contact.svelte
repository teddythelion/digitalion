<script lang="ts">
  import  Section from '../../lib/Section.svelte';
  import  Contact from '../../lib/Contact.svelte';   
  import  ExampleDiv from '../utils/ExampleDiv.svelte'; 
  import  MetaTag from '../utils/MetaTag.svelte';  
  import { Label, Input, Textarea, Button } from 'flowbite-svelte';
  import { GradientButton } from 'flowbite-svelte';
  const breadcrumb_title = 'Digital Lion Media LLC';
  const title = 'Contact';
  const dir = 'landing';
  const description ="Web development and SEO with integrated AI learning.";
 
let status = "";
const handleSubmit = async data => {
  status = 'Submitting...'
  const formData = new FormData(data.currentTarget)
  const object = Object.fromEntries(formData);
  const json = JSON.stringify(object);

  const response = await fetch("https://api.web3forms.com/submit", {
      method: "POST",
      headers: {
          "Content-Type": "application/json",
          Accept: "application/json",
      },
      body: json
  });
  const result = await response.json();
  if (result.success) {
      console.log(result);
      status = result.message || "Success"
  }
}
</script>
   
  

<MetaTag {breadcrumb_title} {title} {dir} {description} />


<ExampleDiv>
  <Section name="contact">
    <Contact>
      <svelte:fragment slot="h2">Contact Us</svelte:fragment>
      <svelte:fragment slot="paragraph">
       We can help you with any technical issues regarding the web. with out a proper web representation you culd be losing 80% for your business. Lets go!
      </svelte:fragment>
      <form  on:submit|preventDefault={handleSubmit} class="space-y-8">
        <div>
          <input type="hidden" name="access_key" value="f5c85264-3cc3-4d54-a810-395c816df460">
          <Label for="email" class="block mb-2">Your email</Label>
          <Input id="email" type ="email" name="email" placeholder="name@digitalionmedia.com" required />
        </div>
        <div>
          <Label for="subject" class="block mb-2">Name</Label>
          <Input
            type="text"
             name="name" 
            id="subject"            
            placeholder="First and or last whatever you prefer."
            required
          />
        </div>
        <div>
          <Textarea
            id="subject"
            name="message" 
            rows="3"
            placeholder="Leave a comment..."
            label="Your message"
          />
        </div>        
        <GradientButton outline color="cyanToBlue" class="w-72" size="xl"><input type="submit" /></GradientButton>
      </form>
      <div>{status}</div>
    </Contact>
  </Section>
</ExampleDiv>
