<template>
  <div class="row justify-center q-pt-sm">
    <q-avatar size="100px">
      <img src="https://cdn.quasar.dev/team/jeff_galbraith.jpg" alt="">
    </q-avatar>
  </div>
  <div class="text-center q-pt-sm">
    <div style="font-weight: 600;">Hieu Chu</div>
    <div style="color: rgba(148,163,184)">chuhueu1@gmail.com</div>
  </div>
  <q-list v-for="navigationItem in navigationItems" :key="navigationItem.id">
    <q-item-label header>
      <div class="text-weight-bolder title">{{navigationItem.title}}</div>
      <div class="subtitle">{{navigationItem.subtitle}}</div>
    </q-item-label>
    <!-- Basic navigation -->
    <Basic :navigation-item = "navigationItem" />
    <!-- Collapse navigation -->
    <Collapse :navigation-item = "navigationItem" />
  </q-list>
</template>

<script>
  import Basic from './components/Basic';
  import Collapse from './components/Collapse';
  export default {
    name: 'Navigation',
    components: {
      Basic,
      Collapse
    },
    data: function () {
      return {
        navigationItems: [
          {
            id: "dashboard",
            title: "Dashboard",
            subtitle: "Employee",
            type: "group",
            children: [
              {
                id: "dashboard.home",
                title: "Home",
                type: "basic",
                icon: "home",
                link: "/"
              },
              {
                id: "dashboard.home.crm",
                title: "CRM Home",
                type: "basic",
                icon: "dashboard",
                link: "/Dashboard2"
              },
              {
                id: "dashboard.pages",
                title: "Pages",
                type: "collapse",
                icon: "pages",
                children: [
                  {
                    id: "dashboard.pages.login",
                    title: "Login",
                    type: "basic",
                    icon: "email",
                    link: "/Login-1",
                  },
                  {
                    id: "dashboard.pages.lock",
                    title: "Lock Screen",
                    type: "basic",
                    icon: "lock",
                    link: "/Lock",
                  }
                ]
              }
            ]
          },
          {
            id: "profile",
            title: "Profile",
            subtitle: "Account & settings",
            type: "group",
            children: [
              {
                id: "profile.account",
                title: "My account",
                type: "basic",
                icon: "person_outline",
                link: "/profile"
              },
              {
                id: "profile.setting",
                title: "Setting",
                type: "basic",
                icon: "settings",
                link: "/setting"
              },
              {
                id: "profile.signout",
                title: "Sign out",
                type: "basic",
                icon: "logout",
                link: "/sign-out"
              },
            ]
          }
        ]
      }
    },
  }
  // interface NavigationItem {
  //   id?: string;
  //   title?: string;
  //   subtitle?: string;
  //   link?: string;
  //   icon?: string;
  //   type?: 'basic' | 'collapse' | 'group' | 'divider';
  //   children?: NavigationItem[];
  // }
</script>

<style lang="scss" scoped>
  .title {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: .05em;
    text-transform: uppercase;
    --tw-text-opacity: 1;
    color: rgb(129, 140, 248);
  }
  .subtitle {
    font-size: 11px;
    line-height: 1;
    color: rgb(156, 163, 175);
    font-weight: 500;
    letter-spacing: 0.06px;
  }
</style>
