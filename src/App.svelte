<script>
  import "smelte/src/tailwind.css";
  import Datatable from "./datatable/DataTable.svelte";
  import data from "./datatable/data/data.js";

  let columndata = [
    // Array of objects
    {
      label: "First Name", // Column name
      field: "fname", // Field name from row
      numeric: false, // Affects sorting
      html: false // Escapes output if false.
    },
    {
      label: "Last Name",
      field: "lname",
      numeric: false,
      html: false
    },
    {
      label: "Age",
      field: "age",
      numeric: true,
      html: false
    },
    {
      label: "State",
      field: "state",
      numeric: false,
      html: false
    },
    {
      label: "Action",
      field: function(data) {
        return (
          '<a class="waves-effect waves-light btn modal-trigger"' +
          ' href="#modal1">Modal</a>'
        );
      },
      numeric: false,
      html: true
    }
  ];
</script>

<Datatable rows={data} title="Customers" columns={columndata} process="local" />
