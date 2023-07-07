<script>
  const db = [
  	{
  		id: 1,
  		title: 'Bro stuck in 360px',
  		desc: 'Get a life lmfao',
  		thumb:
  			'https://cdn.discordapp.com/attachments/1120202303899701340/1126820795503607920/image.png?width=886&height=498'
  	},
  	{
  		id: 2,
  		title: 'Roblos',
  		desc: 'Free robux!!11!',
  		thumb:
  			'https://cdn.discordapp.com/attachments/901424951473623090/1126822269046505513/image.png?width=886&height=498'
  	},
  	{
  		id: 3,
  		title:
  			'Universe Sandbox 2 theme gonna be like: *plays the most chillest sound ever*',
  		desc: 'Best soundtract',
  		thumb:
  			'https://cdn.discordapp.com/attachments/901424951473623090/1126822514870452274/image.png?width=886&height=498'
  	}
  ];
</script>
<!--

  <span class="inline-flex items-center rounded-md bg-gray-50 px-2 py-1 text-xs font-medium text-gray-600 ring-1 ring-inset ring-gray-500/10">Badge</span>
<span class="inline-flex items-center rounded-md bg-red-50 px-2 py-1 text-xs font-medium text-red-700 ring-1 ring-inset ring-red-600/10">Badge</span>
<span class="inline-flex items-center rounded-md bg-yellow-50 px-2 py-1 text-xs font-medium text-yellow-800 ring-1 ring-inset ring-yellow-600/20">Badge</span>
<span class="inline-flex items-center rounded-md bg-green-50 px-2 py-1 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20">Badge</span>
<span class="inline-flex items-center rounded-md bg-blue-50 px-2 py-1 text-xs font-medium text-blue-700 ring-1 ring-inset ring-blue-700/10">Badge</span>
<span class="inline-flex items-center rounded-md bg-indigo-50 px-2 py-1 text-xs font-medium text-indigo-700 ring-1 ring-inset ring-indigo-700/10">Badge</span>
<span class="inline-flex items-center rounded-md bg-purple-50 px-2 py-1 text-xs font-medium text-purple-700 ring-1 ring-inset ring-purple-700/10">Badge</span>
<span class="inline-flex items-center rounded-md bg-pink-50 px-2 py-1 text-xs font-medium text-pink-700 ring-1 ring-inset ring-pink-700/10">Badge</span>
-->
<div class="py-32 px-10">
<div class="py-5">
<main class="h-full overflow-y-auto">
    <div class="container  mx-auto grid">
      <div class="grid gap-6 mb-8">
        <div class="flex items-center justify-center p-4 bg-white rounded-lg shadow-xs dark:bg-gray-800">
          <div>
            <p class="mb-2 text-sm font-medium text-gray-600 dark:text-gray-400">
              Total blog posted
            </p>
            <p class="text-lg font-semibold text-gray-700 dark:text-gray-200">
              {db.length}
            </p>
          </div>
        </div>
      </div>

    </div>
</main>
</div>
  <div class="grid gap-12 lg:grid-cols-2">
    {#each db as post }
    <div key=post.id class="p-1 rounded-xl group sm:flex space-x-6 bg-gray-800 shadow-xl duration-300 hover:scale-[1.01] hover:bg-gray-700 cursor-pointer hover:rounded-2xl">
      <img src={`${post.thumb}`}
      alt="art cover" loading="lazy" width="1000" height="667" class="h-56 sm:h-full w-full sm:w-5/12 object-cover object-top rounded-lg transition duration-500 group-hover:rounded-xl">
      <div class="sm:w-7/12 pl-0 p-5">
        <div class="space-y-2">
          <div class="space-y-4">
            <h4 class="text-2xl font-semibold text-cyan-500 text-left">{post.title}</h4>
            <p class="text-gray-400 text-left">{post.desc}</p>
          </div>
          <a href="blackhole" class="block w-max text-cyan-600">Read more</a>
        </div>
      </div>
    </div>
    {/each}
  </div>
</div>