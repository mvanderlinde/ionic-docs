# ion-infinite-scroll

Infinite Scrollコンポーネントは、ユーザーがページの下部または上部から指定された距離をスクロールしたときに実行されるアクションを呼び出します。

ユーザが定義された距離に達したときに、`ionInfinite` イベントに割り当てられた関数が呼び出されます。この関数がすべてのタスクを完了したら、無限スクロールインスタンスに対して `complete()` メソッドを呼び出す必要があります。

## Infinite Scroll Content

`ion-infinite-scroll`コンポーネントは、無限スクロールのロジックを持っています。コンテンツを表示するには、子コンポーネントが必要です。Ionicは、デフォルトでその `ion-infinite-scroll-content` コンポーネントを使用します。このコンポーネントは、無限スクロールを表示し、無限スクロールの状態に応じて外観を変更します。ユーザが使用しているプラットフォームに応じて最適なスピナーが表示されます。ただし、`ion-infinite-scroll-content` コンポーネントのプロパティを設定することにより、デフォルトのスピナーを変更したり、テキストを追加することができます。

## Custom Content

`ion-infinite-scroll` と `ion-infinite-scroll-content` コンポーネントを分離することで、開発者は必要に応じて独自のコンテンツコンポーネントを作成できます。このコンテンツには、SVG要素から固有のCSSアニメーションを持つ要素まで、あらゆるものを含めることができます。

## Usage with Virtual Scroll

Infinite scroll requires a scroll container to function. When using a virtual scrolling solution, you will need to disable scrolling on the `ion-content` and indicate which element container is responsible for the scroll container with the `.ion-content-scroll-host` class target.

```html
<ion-content scroll-y="false">
  <virtual-scroll-element class="ion-content-scroll-host">
    <!-- Your virtual scroll content -->
  </virtual-scroll-element>
  <ion-infinite-scroll>
    <ion-infinite-scroll-content></ion-infinite-scroll-content>
  </ion-infinite-scroll>
</ion-content>
```

## Interfaces

### InfiniteScrollCustomEvent

While not required, this interface can be used in place of the `CustomEvent` interface for stronger typing with Ionic events emitted from this component.

```typescript
interface InfiniteScrollCustomEvent extends CustomEvent {
  target: HTMLIonInfiniteScrollElement;
}
```