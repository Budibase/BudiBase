<script>
  import { redirect } from "@roxi/routify"
  import { auth } from "stores/portal"

  $: {
    if (!$auth.user) {
      $redirect("./auth/login")
    } else if ($auth.user.builder?.global) {
      $redirect("./portal")
    } else {
      $redirect("./apps")
    }
  }
</script>
