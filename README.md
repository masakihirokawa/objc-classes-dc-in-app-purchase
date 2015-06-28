# DCInAppPurchase

iOSでアプリ内課金をする「DCInAppPurchase」クラスです。

購入対象のプロダクトIDと、呼び出し元のビューを渡して購入／リストア処理を行います。

このクラスの使用には、_StoreKit_ フレームワークが必要になります。

##導入手順

###1. グローバル定義

プロジェクトの _*.pch_ ファイルでクラスのインスタンスを定義し、どこからでも呼び出せるようグローバル化します。

####*.pch

```objective-c
#import "DCInAppPurchase.h"

DCInAppPurchase *inAppPurchase;
```

###2. 初期化

_AppDelegate.m_ でアプリ起動時に初期化します。

####AppDelegate.m

```objective-c
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    inAppPurchase = [[DCInAppPurchase alloc] init];
}
```

###3. アイテム付与部分の実装

_DCInAppPurchase.m_ の 137〜142行目にある _provideContent_ 内に購入完了時の処理を記述します。

####DCInAppPurchase.m

```objective-c
- (void)provideContent:(NSString *)productIdentifier
{
    // TODO: ここでアイテム付与を行う
    
}
```

##使用方法

###アイテムの購入

アイテムのプロダクトIDを渡してアイテムの購入処理を開始します。

```objective-c
[inAppPurchase startPurchase:@"Product ID" view:self.view];
```

###アイテムのリストア

アイテムのプロダクトIDを渡してアイテムのリストア処理を開始します。

```objective-c
[inAppPurchase restorePurchase:@"Product ID" view:self.view];
```
