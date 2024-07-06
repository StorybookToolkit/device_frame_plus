# device_frame_plus

Mockups for common devices.

## Quickstart

Wrap any widget in a `DeviceFrame` widget and give it a `device` (*multiple devices are available from the `Device` accessors*).

```dart
DeviceFrame(
    device: Devices.ios.iPhone11,
    isFrameVisible: true,
    orientation: Orientation.portrait,
    screen: Container(
        color: Colors.blue,
        child: Text('Hello'),
    ),
)
```

## Usage

### Displaying a virtual keyboard

To display a generic simulated virtual keyboard, simply wrap any widget in a `VirtualKeyboard`.

```dart
DeviceFrame(
    device: Devices.ios.iPhone11,
    orientation: orientation,
    screen: VirtualKeyboard(
        isEnabled: true,
        child: // ...
    ),
)
```

### Maintain device media query and theme in an encapsulated app

To make sure that a `WidgetsApp` uses the simulated `MediaQuery` from the simulated devices, set its `useInheritedMediaQuery` property to `true`.

```dart
DeviceFrame(
    device: Devices.ios.iPhone11,
    orientation: orientation,
    screen: Builder(
        builder: (deviceContext) => MaterialApp(
            useInheritedMediaQuery: true,
            theme: Theme.of(context),
        ),
    ),
),
```

### Creating a custom generic device

Various generic devices are available as `DeviceInfo` factories to make it easy to create custom device instances.

#### Phone

```dart
DeviceInfo.genericPhone(
    platform: TargetPlatform.android,
    name: 'Medium',
    id: 'medium',
    screenSize: const Size(412, 732),
    safeAreas: const EdgeInsets.only(
      left: 0.0,
      top: 24.0,
      right: 0.0,
      bottom: 0.0,
    ),
    rotatedSafeAreas: const EdgeInsets.only(
      left: 0.0,
      top: 24.0,
      right: 0.0,
      bottom: 0.0,
    ),
)
```

#### Tablet

```dart
DeviceInfo.genericTablet(
    platform: TargetPlatform.android,
    name: 'Medium',
    id: 'medium',
    screenSize: const Size(1024, 1350),
    safeAreas: const EdgeInsets.only(
      left: 0.0,
      top: 24.0,
      right: 0.0,
      bottom: 0.0,
    ),
    rotatedSafeAreas: const EdgeInsets.only(
      left: 0.0,
      top: 24.0,
      right: 0.0,
      bottom: 0.0,
    ),
)
```

#### Desktop monitor

```dart
DeviceInfo.genericDesktopMonitor(
    platform: TargetPlatform.windows,
    name: 'Wide',
    id: 'wide',
    screenSize: const Size(1920, 1080),
    windowPosition: Rect.fromCenter(
      center: const Offset(
        1920 * 0.5,
        1080 * 0.5,
      ),
      width: 1620,
      height: 780,
    ),
)
```

#### Latptop

```dart
DeviceInfo.genericLaptop(
    platform: TargetPlatform.windows,
    name: 'Laptop',
    id: 'laptop',
    screenSize: const Size(1920, 1080),
    windowPosition: Rect.fromCenter(
      center: const Offset(
        1920 * 0.5,
        1080 * 0.5,
      ),
      width: 1620,
      height: 780,
    ),
)
```

## Available devices

Screenshots for all available devices are [available in the `test/devices` directory](https://github.com/mjablecnik/device_frame_plus/tree/master/test/devices)

## Contributing

### Edit device frames

All frames are designed in a [Figma file](https://www.figma.com/file/WIamxcVDlHvxcCjLvJnwmR/DevicePreview-Frames?node-id=0%3A1).