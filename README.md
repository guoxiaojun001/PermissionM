# PermissionM
Android7.0 关于动态申请权限问题

如果build 版本>=23,就需要考虑一下问题，具体申请权限的方法，参照MainActivity

 if (Build.VERSION.SDK_INT>=Build.VERSION_CODES.M)  {
 
                int resulet =  ContextCompat.checkSelfPermission(MainActivity.this,Manifest.permission.CAMERA);
                if(PackageManager.PERMISSION_GRANTED == resulet){
                    Toast.makeText(MainActivity.this,"授权通过",Toast.LENGTH_SHORT).show();
                    Intent openCameraIntent2 = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
                    startActivityForResult(openCameraIntent2,10);
                }else {
                   Toast.makeText(MainActivity.this,"授权没有通过",Toast.LENGTH_SHORT).show();
                    checkPermissions(needPermissions);
                    }
              }else {
                 Intent openCameraIntent2 = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
                  startActivityForResult(openCameraIntent2,10);
               }
