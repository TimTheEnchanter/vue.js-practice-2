<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Music</template>

    Here's my
    <a href="https://jamesparrott.bandcamp.com/" target="_blank" rel="noopener">bandcamp</a>.
    As you can probably tell, I like weird experimental stuff way too much.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Atari 2600</template>

    I am a huge fan of the Atari 2600. I love playing space games like Encounter at L5, Guardian, Colony 7 and Juno First
    I've taught myself how to hack Atari 2600 roms, it's a pain in the ass but it's rewarding when it actually works. Shoutout to Astro War for being the nastiest piece of spaghetti code I've ever seen in my life.

    <br /><br />

    They can be found <a href="https://github.com/TimTheEnchanter?tab=repositories&q=Atari&type=&language=&sort=" target="_blank" rel="noopener">here</a>.

  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Flash</template>

    For some reason NAIT taught me the in's and out's of Flash and Actionscript.
    This may be slightly cringeworthy but here's one of the end results of that. Wish I still had the games I made. They were very "meme-core" 2012.
    <br />
    <a href="https://www.youtube.com/watch?v=orwJvgPyTgA" target="_blank" rel="noopener">What the heck was I thinking</a>.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>More to come?</template>

    Going to try building this out further with some slightly more exciting things to see. I really like how it's all clicking together so far.
  </WelcomeItem>


</template>
