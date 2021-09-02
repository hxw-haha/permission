# permission
Android 权限申请


PermissionManager.factoryBuilder(this)
        .addPermission(
                Manifest.permission.READ_EXTERNAL_STORAGE,
                Manifest.permission.WRITE_EXTERNAL_STORAGE,
                Manifest.permission.CAMERA)
        .setListener(new IRequestPermissionListener() {
            @Override
            public void onSucceed() {
                showToast("成功");
            }

            @Override
            public void onRefused(List<String> refusedPermission, List<String> foreverRefusedPermission) {
                showToast("全部拒绝权限：" + refusedPermission.toString()
                        + "\n永远拒绝的权限：" + foreverRefusedPermission.toString());
            }
        }).build();
