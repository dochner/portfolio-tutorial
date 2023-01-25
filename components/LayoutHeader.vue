<script setup lang="ts">
const navMenu = ref(null)

const toggleNavMenu = () => {
  // @ts-ignore it exists
  navMenu.value?.classList.toggle('is-open')
}
</script>

<template>
  <header
    id="header"
    class="layout-header"
  >
    <nav class="layout-header__nav container">
      <a
        href="#"
        class="layout-header__nav-logo"
      >Dochner</a>

      <div
        ref="navMenu"
        class="layout-header__nav-menu"
      >
        <ul class="layout-header__nav-menu-list grid">
          <li class="layout-header__nav-menu-item">
            <NuxtLink
              href="#home"
              class="layout-header__nav-menu-link"
              @click="toggleNavMenu"
            >
              <i class="bx bx-home layout-header__nav-icon" />
              Home
            </NuxtLink>
          </li>
          <li class="layout-header__nav-menu-item">
            <NuxtLink
              href="#about"
              class="layout-header__nav-menu-link"
              @click="toggleNavMenu"
            >
              <i class="bx bx-user layout-header__nav-icon" />
              About
            </NuxtLink>
          </li>
          <li class="layout-header__nav-menu-item">
            <NuxtLink
              href="#skills"
              class="layout-header__nav-menu-link"
              @click="toggleNavMenu"
            >
              <i class="bx bx-file layout-header__nav-icon" />
              Skills
            </NuxtLink>
          </li>
          <li class="layout-header__nav-menu-item">
            <NuxtLink
              href="#"
              class="layout-header__nav-menu-link"
              @click="toggleNavMenu"
            >
              <i class="bx bxs-briefcase layout-header__nav-icon" />
              Services
            </NuxtLink>
          </li>
          <li class="layout-header__nav-menu-item">
            <NuxtLink
              href="#"
              class="layout-header__nav-menu-link"
              @click="toggleNavMenu"
            >
              <i class="bx bxs-image-alt layout-header__nav-icon" />
              Portfolio
            </NuxtLink>
          </li>
          <li class="layout-header__nav-menu-item">
            <NuxtLink
              href="#"
              class="layout-header__nav-menu-link"
              @click="toggleNavMenu"
            >
              <i class="bx bxs-message layout-header__nav-icon" />
              Contact me
            </NuxtLink>
          </li>
        </ul>

        <i
          class="bx bx-x layout-header__nav-close"
          role="button"
          @click="toggleNavMenu"
        />
      </div>

      <div class="layout-header__nav-buttons">
        <i
          class="bx bx-menu-alt-right layout-header__nav-toggle"
          role="button"
          title="Toggle Menu"
          @click="toggleNavMenu"
        />
      </div>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
.layout-header {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: var(--color-bg);
  z-index: var(--z-fixed);
  transition: all 0.3s ease;

  &__nav {
    display: flex;
    justify-content: space-between;
    height: var(--header-height);
    align-items: center;
    padding: 1rem 0;

    &-logo,
    &-toggle {
      color: var(--color-title);
      font-weight: var(--font-weight-medium);
    }

    &-logo:hover {
      color: var(--color-primary);
    }

    &-toggle {
      font-size: 1.1rem;
      cursor: pointer;

      &:hover {
        color: var(--color-primary);
      }
    }
  }
}

@media screen and (max-width: 767px) {
  .layout-header {
    &__nav-menu {
      position: fixed;
      bottom: -100%;
      left: 0;
      width: 100%;
      background-color: var(--color-bg);
      padding: 2rem 1.5rem 4rem;
      box-shadow: 0 -1px 4px rgba(0, 0, 0, .15);
      border-radius: 1.25rem 1.25rem 0 0;
      transition: .3s ease-in-out;

      &.is-open {
        bottom: 0;
      }

      &-list {
        grid-template-columns: repeat(3, 1fr);
        gap: 2rem;
      }

      &-item {
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &-link {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-size: var(--font-size-sm);
        color: var(--color-title);
        font-weight: var(--font-weight-medium);
        transition: .3s ease-in-out;

        &:hover {
          color: var(--color-primary);
        }
      }
    }

    &__nav-icon {
      font-size: 1.2rem;
    }

    &__nav-close {
      position: absolute;
      right: 1.3rem;
      bottom: 0.896rem;
      font-size: 1.5rem;
      color: var(--color-primary);
      cursor: pointer;

      &:hover {
        color: var(--color-accent);
      }
    }
  }
}
</style>
