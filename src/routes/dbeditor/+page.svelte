
<script lang="ts">
    import { onMount } from 'svelte';
    import { RS1 } from '$lib/RS';
    
  
    let tableNames: any = [];
  
    onMount(async () => {
      try {
        // Call the ReqTiles function to get table names
        tableNames = await RS1.ReqTiles();
        console.log(tableNames)
        
        
      } catch (error) {
        console.error('Error fetching table names:', error);
      }
  
      
    });
  </script>
  
  <main>
     <h1>Tables</h1>
      
    </main>
  
  
  