# notiprompt
A prompt component for Notivue, the beautiful toast notification system by smastrom.


This component uses the composition API and tries to keep the adjustments
to a minimum and the implementation as straightforward as possible.



  
<pre>
##In App.vue

  
  import Prompt from '@/components/Prompt.vue'
  


  Since apparently there isn't a slot to place custom content in the Notification 
  component of Notivue, a v-if is used to switch between Notification and Prompt.
  
  &lt;Notivue v-slot="item"&gt;
    &lt;Prompt v-if="item.props.prompt" :item="item"/&gt;
    &lt;Notification v-else :item="item"/&gt;
  &lt;/Notivue&gt;
  
    
</pre>

<pre>
  #Use it

  import { push } from 'notivue'


    push.success({
      title:'Prompt',
      message: "Hi, I'm feeling fckng great",
      props: {
        prompt: true,
        buttons: [
                {
                  'label': 'Print',
                  'style':'info',
                  'icon':'mdi mdi-printer',
                  'onclick': function (item) {
                    console.log(item);  
                  }
                },

                {
                  'label': 'Close',
                  'style':'danger',
                  'icon':'mdi mdi-close',
                  'onclick': function (item) {
                    item.clear();
                  }
                }
        ]
      }
    });


    push.promise({title:'Toast','message':'Hi, I'm feeling fckng great'});
  

  
  
</pre><img src="https://github.com/chimendoza/notiprompt/assets/10203997/b6c7ee67-f651-474e-bb23-784cb904a4e5"/>

