<template>
  <section class="py-24 px-6 bg-gray-50">
    <div class="max-w-6xl mx-auto">

      <div class="flex flex-col md:flex-row md:items-center md:justify-between gap-4 mb-8">
        <div>
          <p class="text-sm mb-4 text-emerald font-bold bg-emerald-pale inline-block px-5 py-1 rounded-md font-['Plus_Jakarta_Sans']">
        LIVE PREVIEW
          </p>
          <h2 class="text-4xl font-bold mb-2">
            See it in action
          </h2>

          <p class="text-gray-500">
            Try searching andd filtering contacts in real-time.
          </p>
        </div>

        <input
          v-model="search"
          type="text"
          placeholder="Search contacts"
          class="border border-gray-300 rounded-xl px-5 py-3 w-full md:w-80 bg-white"
        />
      </div>
      <p class="mt-6 mb-3 text-gray-500">
        Showing {{ filteredContacts.length }} of contacts.
      </p>
      <div class="overflow-x-auto bg-white rounded-2xl shadow-lg">

        <table class="w-full">

          <thead class="bg-gray-100 text-left">
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
              class="border-t border-gray-100 hover:bg-gray-50"
            >
              <td class="p-5">
                {{ contact.name }}
              </td>

              <td class="p-5 text-gray-500">
                {{ contact.email }}
              </td>

              <td class="p-5">
                <span
                  class="px-4 py-2 rounded-full text-sm font-medium"
                  :class="
                    contact.status === 'Active'
                      ? 'bg-green-100 text-green-700'
                      : 'bg-red-100 text-red-700'
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
          status: 'Active',
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