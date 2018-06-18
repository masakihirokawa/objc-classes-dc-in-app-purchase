# DCInAppPurchase

iOSでアプリ内課金をする「DCInAppPurchase」クラスです。

購入対象のプロダクトIDと、呼び出し元のビューを渡して購入／リストア処理を行います。

このクラスの使用には、_StoreKit_ フレームワークが必要になります。

## 導入手順

### アイテム付与部分の実装

_DCInAppPurchase.m_ の 137〜142行目にある _provideContent_ 内に購入完了時の処理を記述します。

#### DCInAppPurchase.m

```objective-c
- (void)provideContent:(NSString *)productIdentifier
{
    // TODO: ここでアイテム付与を行う
    
}
```

## 使用方法

### アイテムの購入

アイテムのプロダクトIDを渡してアイテムの購入処理を開始します。

```objective-c
DCInAppPurchase *inAppPurchase = [[DCInAppPurchase alloc] init];
[inAppPurchase startPurchase:@"Product ID" view:self.view];
```

### アイテムのリストア

アイテムのプロダクトIDを渡してアイテムのリストア処理を開始します。

```objective-c
DCInAppPurchase *inAppPurchase = [[DCInAppPurchase alloc] init];
[inAppPurchase restorePurchase:@"Product ID" view:self.view];
```
