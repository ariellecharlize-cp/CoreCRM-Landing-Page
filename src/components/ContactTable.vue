<template>
  <section class="py-24 px-6 bg-emerald-mint">
    <div class="max-w-6xl mx-auto">

    <div class="max-w-6xl mx-auto text-center">

     <p class="text-sm mb-4 text-emerald font-bold bg-emerald-light inline-block px-5 py-2 rounded-full">
        LIVE PREVIEW
     </p>
      <h2 class="text-4xl text-emerald-dark font-bold mb-4">
        See it in action
      </h2>

      <p class="text-emerald mb-10">
        Try searching and filtering contacts in real-time.
      </p>
    </div>

  <div class="card bg-white rounded-2xl p-10">
        
    <div class="flex felx-col md:flex-row items-center justify between gap-7">
        <input
          v-model="search"
          type="text"
          placeholder="Search contacts..."
          class="border-2 border-emerald-pale bg-emerald-mint rounded-xl px-5 py-3 w-full md:w-190"
        />
        <button class="text-emerald font-bold border-2 border-emerald-pale bg-emerald-mint rounded-xl px-5 py-3 w-full md:w-60 hover:bg-emerald hover:text-white"> All Status </button>
    </div>
      <p class="mt-6 mb-3 text-emerald font-bold">
        Showing {{ filteredContacts.length }} of contacts.
      </p>


      <div class="overflow-x-auto bg-white rounded-2xl border-1 border-emerald-pale">
        <table class="w-full">

          <thead class="bg-emerald-mint text-left text-emerald-medium border-1 border-emerald-pale">
            <tr>
              <th class="p-5">NAME</th>
              <th class="p-5">EMAIL</th>
              <th class="p-5">STATUS</th>
              <th class="p-5">ACTION</th>
            </tr>
          </thead>

          <tbody>
            <tr
              v-for="(contact, index) in filteredContacts"
              :key="index"
              class="border-1 border-emerald-pale hover:bg-emerald-100"
            >

              <td class="p-5">
                <div class="flex items-center gap-3">
                  
                  <div
                    class="w-10 h-10 rounded-full bg-emerald-pale text-emerald-700 flex items-center justify-center font-bold"
                  >
                    {{ contact.name.split(' ').map(n => n[0]).join('') }}
                  </div>

                  <span class="text-emerald-medium font-bold">
                    {{ contact.name }}
                  </span>

                </div>
              </td>

              <td class="p-5 text-emerald">
                {{ contact.email }}
              </td>

              <td class="p-5">
                <span
                  class="px-4 py-1 rounded-full text-sm font-bold"
                  :class="
                    contact.status === 'Active'
                      ? 'bg-green-100 text-emerald'
                      : contact.status === 'Inactive'
                      ? 'bg-red-100 text-red-500'
                      : 'bg-amber-100 text-amber-600'
                  "
                >
                  {{ contact.status }}
                </span>
              </td>

              <td class="p-5 text-emerald-500 font-bold">
                {{ contact.action }}
              </td>

            </tr>
          </tbody>

        </table>

      </div>

    </div>
    </div>
  </section>
</template>


<script>
export default {
  name: 'ContactTable',

  data() {
    return {
      search: '',

      contacts: [
        {
          name: 'Ana Santos',
          email: 'ana@company.co',
          status: 'Active',
          action: 'View'
        },
        {
          name: 'Marco Reyes',
          email: 'marco@startup.io',
          status: 'Pending',
          action: 'View'
        },
        {
          name: 'Jana Dela Cruz',
          email: 'jane@agency.ph',
          status: 'Active',
          action: 'View'
        },
        {
          name: 'Kim Lee',
          email: 'kim@design.com',
          status: 'Inactive',
          action: 'View'
        },
      ],
    }
  },

  computed: {
    filteredContacts() {
      return this.contacts.filter((contact) =>
        contact.name.toLowerCase().includes(this.search.toLowerCase())
      )
    },
  },

  watch: {
    search(newValue) {
      console.log('Searching:', newValue)
    },
  },
}
</script>