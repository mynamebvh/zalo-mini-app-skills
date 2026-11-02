# ZAUI — Verified usage examples

The examples below use the API of `zmp-ui@1.11.15-2`. They supplement the props tables in `references/`.

## 1. App shell, router, and provider

```jsx
// App.jsx
import React from "react";
import { App, SnackbarProvider, ZMPRouter, AnimationRoutes, Route } from "zmp-ui";
import HomePage from "./pages/HomePage";
import DetailPage from "./pages/DetailPage";

export default function AppRoot() {
  return (
    <App>
      <SnackbarProvider>
        <ZMPRouter>
          <AnimationRoutes>
            <Route path="/" element={<HomePage />} />
            <Route path="/detail/:id" element={<DetailPage />} />
          </AnimationRoutes>
        </ZMPRouter>
      </SnackbarProvider>
    </App>
  );
}
```

## 2. Page, Header, and BottomNavigation

```jsx
import React, { useState } from "react";
import { Page, Header, BottomNavigation, Icon } from "zmp-ui";

export default function HomePage() {
  const [activeTab, setActiveTab] = useState("home");

  return (
    <Page>
      <Header title="Home" showBackIcon={false} />

      <div style={{ paddingBottom: 72 }}>
        {/* Screen content */}
      </div>

      <BottomNavigation
        fixed
        activeKey={activeTab}
        onChange={(key) => setActiveTab(key)}
      >
        <BottomNavigation.Item
          key="home"
          label="Home"
          icon={<Icon icon="zi-home" />}
        />
        <BottomNavigation.Item
          key="profile"
          label="Profile"
          icon={<Icon icon="zi-user" />}
          activeIcon={<Icon icon="zi-user-solid" />}
        />
      </BottomNavigation>
    </Page>
  );
}
```

## 3. Navigation with useNavigate

```jsx
import { useNavigate } from "zmp-ui";

function ProductCard() {
  const navigate = useNavigate();

  return (
    <button
      onClick={() =>
        navigate("/detail/123", {
          state: { from: "home" },
          animate: true,
          direction: "forward",
        })
      }
    >
      View details
    </button>
  );
}
```

`navigate(-1)` is equivalent to the back button.

## 4. Tabs

```jsx
import React from "react";
import { Page, Tabs, List, Avatar, Icon } from "zmp-ui";

export default function ContactsPage() {
  return (
    <Page>
      <Tabs id="contacts">
        <Tabs.Tab key="friends" label="Friends">
          <List>
            <List.Item
              title="John Doe"
              subTitle="Active"
              prefix={<Avatar> A </Avatar>}
              suffix={<Icon icon="zi-call" />}
            />
          </List>
        </Tabs.Tab>
        <Tabs.Tab key="groups" label="Groups">
          Group list
        </Tabs.Tab>
      </Tabs>
    </Page>
  );
}
```

With many tabs, add `scrollable`. You can replace `Tabs.Tab` with the `items` prop.

## 5. List

```jsx
import { Page, List, Avatar } from "zmp-ui";

const users = [
  { id: 1, name: "Alex", online: true },
  { id: 2, name: "Ben", online: false },
];

export default function UserList() {
  return (
    <Page>
      <List
        dataSource={users}
        renderItem={(user) => (
          <List.Item
            key={user.id}
            title={user.name}
            subTitle={user.online ? "Online" : "Offline"}
            prefix={<Avatar online={user.online}>{user.name[0]}</Avatar>}
          />
        )}
      />
    </Page>
  );
}
```

## 6. Basic form

```jsx
import React, { useState } from "react";
import {
  Page, Box, Stack, Button, Input, Select, Checkbox, Radio, Switch,
} from "zmp-ui";

export default function ProfileForm() {
  const [name, setName] = useState("");
  const [city, setCity] = useState("hcm");
  const [interests, setInterests] = useState([]);
  const [gender, setGender] = useState("male");
  const [notifications, setNotifications] = useState(true);

  return (
    <Page>
      <Stack space={16}>
        <Input
          label="Full name"
          value={name}
          onChange={(e) => setName(e.target.value)}
          helperText="Enter your display name"
        />

        <Input.Password
          label="Password"
          helperText="At least 8 characters"
          visibilityToggle
        />

        <Input.Search
          label="Search"
          placeholder="Enter a keyword"
          onSearch={(text) => console.log(text)}
        />

        <Select
          label="City"
          value={city}
          onChange={(value) => setCity(value)}
          placeholder="Select a city"
        >
          <Select.Option value="hcm" title="Ho Chi Minh City" />
          <Select.Option value="hn" title="Hanoi" />
          <Select.Option value="dn" title="Da Nang" />
        </Select>

        <Checkbox.Group
          name="interests"
          value={interests}
          onChange={(value) => setInterests(value)}
          options={[
            { label: "Music", value: "music" },
            { label: "Travel", value: "travel" },
            { label: "Sports", value: "sport" },
          ]}
        />

        <Radio.Group
          name="gender"
          value={gender}
          onChange={(value) => setGender(value)}
          options={[
            { label: "Male", value: "male" },
            { label: "Female", value: "female" },
          ]}
        />

        <Switch
          label="Notifications"
          checked={notifications}
          onChange={(checked) => setNotifications(checked)}
        />

        <Button variant="primary" fullWidth>
          Save
        </Button>
      </Stack>
    </Page>
  );
}
```

Note: `Switch` passes the remaining props to `input[type="checkbox"]`, so `checked` / `onChange` follow the standard React input convention.

## 7. Multiple selection with Select

```jsx
const [values, setValues] = useState([]);

<Select
  multiple
  value={values}
  onChange={(selected) => setValues(selected)}
  label="Interests"
  placeholder="Select multiple items"
>
  <Select.Option value="music" title="Music" />
  <Select.Option value="travel" title="Travel" />
  <Select.Option value="sport" title="Sports" />
</Select>
```

If you need to group options, the package exports `Select.OtpGroup` (the name has the "Ot" prefix due to the package API; it is not `OptGroup`):

```jsx
<Select.OtpGroup label="Group 1">
  <Select.Option value="1" title="Option 1" />
</Select.OtpGroup>
```

## 8. DatePicker and Picker

```jsx
import React, { useState } from "react";
import { Page, Stack, DatePicker, Picker } from "zmp-ui";

export default function DateAndCityPicker() {
  const [date, setDate] = useState(new Date());
  const [city, setCity] = useState(null);

  return (
    <Page>
      <Stack space={16}>
        <DatePicker
          label="Date of birth"
          value={date}
          onChange={(value) => setDate(value)}
          dateFormat="dd/mm/yyyy"
        />

        <Picker
          label="City"
          value={city}
          onChange={(value) => setCity(value)}
          data={[
            {
              name: "city",
              options: [
                { key: "hcm", value: "hcm", displayName: "Ho Chi Minh City" },
                { key: "hn", value: "hn", displayName: "Hanoi" },
                { key: "dn", value: "dn", displayName: "Da Nang" },
              ],
            },
          ]}
        />
      </Stack>
    </Page>
  );
}
```

`Picker` accepts `data` as an array of columns; `value` / `onChange` use an object keyed by the column's `name`.

## 9. Modal

```jsx
import React, { useState } from "react";
import { Page, Button, Modal } from "zmp-ui";

export default function DeleteButton() {
  const [visible, setVisible] = useState(false);

  return (
    <Page>
      <Button type="danger" onClick={() => setVisible(true)}>
        Delete
      </Button>

      <Modal
        visible={visible}
        title="Delete this item?"
        description="This action cannot be undone."
        onClose={() => setVisible(false)}
        actions={[
          { text: "Cancel", close: true },
          {
            text: "Delete",
            danger: true,
            close: true,
            onClick: () => console.log("deleted"),
          },
        ]}
      />
    </Page>
  );
}
```

## 10. Sheet and ActionSheet

```jsx
import React, { useState } from "react";
import { Page, Button, Sheet } from "zmp-ui";

export default function FilterSheet() {
  const [visible, setVisible] = useState(false);

  return (
    <Page>
      <Button onClick={() => setVisible(true)}>Open filters</Button>

      <Sheet
        visible={visible}
        onClose={() => setVisible(false)}
        title="Filters"
      >
        Filter content
      </Sheet>
    </Page>
  );
}
```

```jsx
<Sheet.Actions
  visible={visible}
  title="Choose an action"
  onClose={() => setVisible(false)}
  actions={[
    [
      { text: "Share", onClick: () => console.log("share") },
      { text: "Save", highLight: true },
    ],
    [{ text: "Cancel", close: true, danger: true }],
  ]}
/>
```

## 11. Snackbar

```jsx
import React from "react";
import { Page, Button, useSnackbar } from "zmp-ui";

export default function SaveButton() {
  const { openSnackbar } = useSnackbar();

  return (
    <Page>
      <Button
        onClick={() =>
          openSnackbar({
            text: "Saved successfully",
            type: "success",
            duration: 3000,
          })
        }
      >
        Save
      </Button>
    </Page>
  );
}
```

`useSnackbar` must be inside `SnackbarProvider` (see section 1).

## 12. Light / dark theme

```jsx
import { useTheme, Button } from "zmp-ui";

export function ThemeToggle() {
  const [theme, setTheme] = useTheme();

  return (
    <Button
      onClick={() => setTheme({ mode: theme === "light" ? "dark" : "light" })}
    >
      {theme === "light" ? "Dark mode" : "Light mode"}
    </Button>
  );
}
```

## 13. Layout containers

```jsx
import { Page, Box, Stack, Cluster, Center, Grid } from "zmp-ui";

<Page>
  <Stack space={12}>
    <Box p={16}>Box with padding according to the spacing system</Box>

    <Cluster space={8}>
      <Button size="small">One</Button>
      <Button size="small">Two</Button>
    </Cluster>

    <Center>
      <Button>Centered button</Button>
    </Center>

    <Grid columnCount={2} columnSpace={8} rowSpace={8}>
      <Box>Cell 1</Box>
      <Box>Cell 2</Box>
    </Grid>
  </Stack>
</Page>
```

## 14. Notes on differences between documentation and package

- `Sheet.Actions` is the correct name in the package for ActionSheet; the documentation sometimes writes `const { Action } = Sheet`.
- `Select.OtpGroup` is the actual export name for the option group; the documentation's props table calls it `OptGroupProps`.
- `Input.OTP` accepts `onChange` as an event; read the code via `event.target.value`.
- `DatePicker.onChange` receives `(date, pickerValue)`; the first parameter is a `Date`.
- For props not in the documentation's table, check the reference file first; do not guess.
