<script>
import Icon from 'svelte-awesome/components/Icon.svelte'
import { github, twitter, linkedin, instagram } from 'svelte-awesome/icons';
import { faGrimace } from '@fortawesome/free-regular-svg-icons';

</script>
<style>
li {
  text-decoration: none;
  display: inline-block;
}
/* li + li:before {
    content: " • ";
} */
</style>


<li><a href="https://github.com/mrgnw"><Icon data={github}/></a></li>
<li><a href="https://twitter.com/mrgnw"><Icon data={twitter}/></a></li>
<li><a href="https://linkedin.com/in/mrgnw"><Icon data={linkedin}/></a></li>
<li><a href="https://instagram.com/mrgnw2"><Icon data={instagram}/></a></li>