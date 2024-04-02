<script>


    const name = "Arvind";
    const hack =`<a href="#" onclick="alert('you have been haked!!!')">win a price!<a/>`
    const id = "heading";
    const disabled = true;
    const status ="success";
    const isPromoted = true;
    
    // if else
    
    
    const num = "p";
    // const num = 8;
    // const num = 0;
    // const num = -5;
    
    // for each
    
    const names = ['arvind', 'abhis', 'abjith']
    
    const fullName = [
    	{first:'arvind' , last:'wr'},
    	{first:'prmak' , last:'jr'},
    	{first:'rrihg' , last:'lr'},
    ]
    
    // count change
    
    let count = 0
    
    function handleClick(event,stepSize) {
    	console.log(event)
    	count += stepSize
    }
    
    
    // forms
    const formValues ={
    	name:'',
        email:'',
    	profileSummary:'',
    	country:'',
    	jobLocation:[],
    	remoteWork:false,
    	skillSet:[],
    	yearsOfExperience:'',
    }
    
    function submitForm(event) {
    	event.preventDefault()
        console.log(formValues)
    }
    
    
    // reactive bindings
    
    let firstName = "arvind";
    let lastName = "M";
    
     $:fullname = `${firstName} ${lastName}`
    
    
    let volume = 0
    
    $: if (volume <0){
    	alert(`cant go lower`)
    	volume=0
    }else if(volume>20){
    	alert(`cant go higher`)
        volume=20
    }
    
    
    // import components
    
    import Greet from "./components/greet.svelte";
    
    
    import Popup from "./components/Popup.svelte";
    
    let showPopup = false;
    
    
    
    import Outer from "./components/outer.svelte";
    import Button from "./components/button.svelte";
    
     function handleGreet(event) {
    	alert(event.detail);
     }
    
    
    import Card from "./components/card.svelte";
    
    
    import NameList from "./components/nameList.svelte";
    import ChildStyles from "./components/ChilsStyles.svelte";
    
    import PostList from "./components/postList.svelte";
    
    import AutoFous from "./components/AutoFous.svelte";
    import TabA from "./components/TabA.svelte";
    import TabB from "./components/TabB.svelte";
    import TabC from "./components/TabC.svelte";
    
    
    let activeTab = TabA
    
    
 import Counter,{getTotalCount} from "./components/Counter.svelte";


        import Display from "./components/Display.svelte";
        import Increment from "./components/Increment.svelte";
        import Decrement from "./components/Decrement.svelte";
        import Reset from "./components/Reset.svelte";


    </script>
    
    
    
        <main >	


       
            <h1>hello {name} !</h1> 
                     
                             <h3>App component global styles</h3>
                             <h4>App component Text</h4>
                             <ChildStyles/> 
                         <NameList>
                         <h2 slot="hero" let:firstName let:lastName> {firstName} {lastName}</h2>
                     </NameList>
                     <NameList>
                         <h2 slot="hero" let:firstName let:lastName>{lastName} {firstName}</h2>
                     </NameList>
                     <NameList>
                         <h2 slot="hero" let:firstName >{firstName}</h2>
                     </NameList>
                    <Card content ="card content 1"/>
                             <Card content ="card content 2"/> 
                     
                             <Card class="text-white text-5xl">Card content</Card>
                             <Card><h2>Card content</h2></Card>
                             <Card><img src="https://picsum.photos/200" alt="#"></Card>
                             <Card></Card>
                     
                     
                             <Card><div slot="header"><h3>Header</h3></div>
                             <div slot="content"><img src="https://picsum.photos/200" alt="#"></div>
                         <hr />
                             <div slot="footer"><button>View details</button></div>
                             </Card>
                    <Outer on:greet={handleGreet}/>
                             <Button on:click={()=>alert('Clicked')}>Click</Button>
                     
                         
                     
                     
                     
                     
                    
                         <p> {@html hack}</p>
                         <h2 {id}>this is a headind with a ID</h2>
                         <button disabled={disabled}>Bind</button>
                         <h2 class={status}>status</h2>
                         <h2 class={isPromoted ? `promoted` : ''}>Movie Title</h2>
                     
                         if else
                     
                         {#if num === 0}
                            <h2>the number is zero!! </h2>
                         {:else if num < 0}
                             <h2>the number is negative </h2>
                         {:else if num > 0}
                             <h2>the number is positive</h2>
                         {:else}
                             <h2>this is not a number</h2>
                         {/if}
                     
                         <!-- for each -->
                     
                         {#each fullName as name,index}
                         <h2>{index+ 1 } {name.first} {name.last}</h2>
                             
                         {/each}
                     
                         {#each names as name,index}
                         <h2>{index+ 1 } {name}</h2>
                         {/each}
                     
                         <!-- change count -->
                     <button on:click ={()=>count = count +1}>Count {count}</button>
                     <button on:click={ (event) =>handleClick(event,5)}>count{count}</button>
                     <button on:click={ (event) =>handleClick(event,10)}>count{count}</button>
                     
                         <div>
                    <pre class="text-white">
                        {JSON.stringify(formValues,null,4)}
                    </pre>
                             </div>
                             <form on:submit={submitForm}>
                    <div>
                        <label for="name" class="text-white">Name</label>
                        <input type="text" id="name" bind:value={formValues.name}>
                        <label for="mail">Email</label>
                        <input type="email" id= "mail" bind:value={formValues.email}>
                    </div>
                    <div>
                        <label for="profile" class="text-white">Profile summary</label>
                        <textarea  id="profile"  bind:value={formValues.profileSummary}></textarea>
                    </div>
                    <div>
                        <label for="country "  class="text-white">Country</label>
                        <select	 id="country" bind:value={formValues.country}>
                            <option value="select">		Select a country</option>
                            <option value="india">India</option>
                            <option value="usa">USA</option>
                            <option value="australia">Australia</option>
                            <option value="canada">Canada</option>
                            <option value="australia">Australia</option>
                        </select>
                    </div>
                    <div>
                        <label for="job-location"  class="text-white">jobLocation</label>
                        <select	 id="job-location" bind:value={formValues.jobLocation} multiple>
                            <option value="">Select a country</option>
                            <option value="india">India</option>
                            <option value="usa">USA</option>
                            <option value="australia">Australia</option>
                            <option value="canada">Canada</option>
                            <option value="australia">Australia</option>
                        </select>
                    </div>
                 
                    <div>
                        <input type="checkbox" id="remoteWork" bind:checked={formValues.remoteWork}>
                        <label for="remoteWork">Open to remote work ?</label>
                    </div>
                    <div>
                        <label class="text-white ">skill set</label>
                        <input type="checkbox" id="html" value="html" bind:group={formValues.skillSet}>
                        <label for="html">HTML</label>
                        <input type="checkbox" id="css" value="css" bind:group={formValues.skillSet}>
                        <label for="css">CSS</label>
                        <input type="checkbox" id="javascript" value="javascript" bind:group={formValues.skillSet}>
                        <label for="javascript">Javascript</label>
                    </div>
                    <div>
                        <label class="text-white">years of experience</label>
                        <input type="radio" id="0-2" value="0-2" bind:group={formValues.yearsOfExperience}/>
                        <label for="0-2">0-2</label>
                        <input type="radio" id="3-5" value="3-5" bind:group={formValues.yearsOfExperience}/>
                        <label for="3-5">3-5</label>
                        <input type="radio" id="6-10" value="6-10" bind:group={formValues.yearsOfExperience}/>
                        <label for="6-10">6-10</label>
                    </div>
                    <div>
                        <button>Submit</button>
                    </div>
                             </form>	
                     
                             <h2>{firstName} {lastName}</h2>
                             <h2>{fullname}</h2>
                             <button on:click={() =>{firstName ='M' ,lastName = 'Arvind'}}>Change name</button>
                  <h2> current volume {volume}</h2>
                  <button on:click={()=>(volume += 2)}>Increase volume +</button>
                  <button on:click={()=>(volume -= 2)}>Decrease volume -</button>
                     <Greet name ="arvind"/>
                       <Greet name ="abhi"/>
                     
                     
                     
                     
                            <button on:click={()=>(showPopup=true) }>
                             show Popup
                            </button>
                     
                     
                             {#if showPopup}
                             <Popup on:close ={()=>(showPopup=false)}/>
                             {/if}



                             <Display/>
                             <Increment/>
                             <Decrement/>
                             <Reset/>
                         
                          
                         
                                
            <button on:click={()=> alert(getTotalCount())}>Alert total count</button>
                        <Counter></Counter>
                        <Counter></Counter>
                        <Counter></Counter>
                <button on:click={()=>(activeTab = TabA)}>Tab A</button>
                        <button on:click={()=>(activeTab = TabB)}>Tab B</button>
                        <button on:click={()=>(activeTab = TabC)}>Tab C</button>
                
                
                <svelte:component this={activeTab}></svelte:component> 
                
                    {#if activeTab === 'TabA'}
                        
                        
                        <TabA></TabA>
                    {/if}
                    {#if activeTab === 'TabB'}
                        <TabB></TabB>
                    {/if}
                    {#if activeTab === 'TabC'}
                        <TabC></TabC>
                    {/if} 
                
                        <AutoFous/> 
                <PostList/> 
             </main>
    
    
    <style>
    
    :global(h3) {
        color: aqua;
    }
        h4{
            color:orange;
            font-size: 50px;
    
        }
        input +label {
            display: inline-flex;
            color: aliceblue;
    
        }
    
        :global(main) {
            text-align: center; 
            padding: 1em;
            max-width: 240px;
            margin: 0 auto;
            height: 100vh;
        
        }
        #heading {
            color:paleturquoise;
            font-size: 5em;
        }
    
        .danger{
            color:red;
            font-size: 5em;
        }
        .success{
            color:green;
            font-size: 5em;
        }
        .promoted{
            font-style: italic;
            font-size: 10em;
            color:greenYellow;
        }
        p{
            font-size: 3em;
            color: aqua;
        }
    
        h1 {
            color: #ff3e00;
            text-transform: capitalize;
            font-size: 10em;
            font-weight: 100;
        }
        :global(h2){
            color:rgb(196, 121, 28);
            text-transform: capitalize;
            font-size: 50px;
            font-weight: 100;
        }
        :global(button){
            background-color:rgb(225, 186, 15);
            color: rgb(200, 47, 47);
            border: 2px solid firebrick ;
            font-size: 2rem;
            padding: 20px 40px;
        }
        img{
    
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin: 0 auto;
        }
    
        @media (min-width: 640px) {
            main {
                max-width: none;
            }
        }
    </style>