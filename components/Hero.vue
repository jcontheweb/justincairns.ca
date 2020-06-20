<template>
  <div>
    <h1 class="font-bold text-2xl sm:text-4xl lg:text-5xl leading-tight">
      I create websites that
      <br />
      <span class="text-green-500">actualize your idea</span>.
    </h1>
    <div class="mt-8">
      <p
        class="text-lg sm:text-2.5vw lg:text-3xl leading-tight"
      >Hi I'm Justin, a web developer who specializes in producing accessible user interfaces.</p>
      <p
        class="text-lg sm:text-2.5vw lg:text-3xl mt-6 leading-tight"
      >I'm currently available for freelance & contract work. I'll also be considering full-time remote position offers from within Canada & UK.</p>
    </div>
    <div class="mt-8">
      <span class="text-xl leading-none mr-4">Have an idea? 💡</span>
      <a
        href="mailto:contact@justincairns.ca"
        class="chat inline-block relative text-green-500 font-medium text-xl sm:text-2xl leading-none"
      >Let's chat</a>
    </div>
  </div>
</template>

<style lang="scss">
.chat:after {
  @apply absolute inset-x-0 bg-green-500 opacity-25;
  content: "";
  height: 66.6666%;
  transform: translate(-4.5%, 55%);
}
</style>