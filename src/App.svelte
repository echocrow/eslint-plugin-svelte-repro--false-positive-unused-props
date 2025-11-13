<script lang="ts" module>
export class FooController<T extends string = string> {
  #foo: T

  constructor(foo: T) {
    this.#foo = foo
  }

  onclose() {
    console.info(this.#foo)
  }
}
</script>

<script lang="ts">
interface Props {
  ctrl: FooController
}
let {ctrl}: Props = $props()

function onclose() {
  ctrl.onclose()
}
</script>

<dialog {onclose}>Foo</dialog>
