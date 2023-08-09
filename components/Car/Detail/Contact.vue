<template>
    <div class="mt-15 pt-5">
      <div class="flex w-full justify-between">
        <input type="text" class="p-1 border w-1/4 rounded" placeholder="Name" />
        <input type="text" class="p-1 border w-1/4 rounded" placeholder="Email" />
        <input type="text" class="p-1 border w-1/4 rounded" placeholder="Phone" />
      </div>
      <div class="flex mt-4">
        <textarea class="p-1 w-full resize-none h-20 border rounded" placeholder="Message"></textarea>
      </div>
      <button
        type="submit"
        class="bg-slate-800 text-white px-10 py-3 rounded mt-4"
      >
        Submit
      </button>
    </div>
</template>