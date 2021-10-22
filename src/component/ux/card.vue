<template>
  <section>
    <slot></slot>
  </section>
</template>

<style>
section {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  width: 40%;
  left: 30%;
  top: 20vh;
  position: fixed;
  background-color: white;
  padding: 1.5rem;
  text-align: left;
  border-radius: 1rem;
}
button {
  padding: 1rem;
  background-color: #ffbcbc;
  border: none;
  cursor: pointer;
  color: #23049d;
  font-size: 1rem;
  font-family: roboto;
  font-weight: 500;
}
button:hover {
  background-color: #23049d;
  color: white;
}
</style>
