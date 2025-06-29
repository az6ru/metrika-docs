# Целевые события на Яндексе | API Яндекс Метрики

      * Посетители
Электронная коммерция

  1. [API отчетов](../index.md)
  2. [Шаблоны](../presets.md)
  3. Электронная коммерция

# Электронная коммерция

**Шаблон** |  **Отчет** |  **Группировки** |  **Метрики**  
---|---|---|---  
`top_products` |  Популярные товары |  `ym:s:productName` |  `ym:s:productImpressions`, `ym:s:productImpressionsUniq`, `ym:s:productBasketsQuantity`, `ym:s:productPurchasedQuantity`  
`top_brands` |  Популярные категории и бренды |  `ym:s:productCategoryLevel1`, `ym:s:productBrand`, `ym:s:productName` |  `ym:s:productImpressions`, `ym:s:productImpressionsUniq`, `ym:s:productBasketsQuantity`, `ym:s:productPurchasedQuantity`  
`basket` |  Товары в корзине |  `ym:s:productName` |  `ym:s:productBasketsQuantity`, `ym:s:productBasketsUniq`, `ym:s:productBaskets<currency>ConvertedPrice`, `ym:s:productPurchasedQuantity`  
`purchase` |  Источники заказов |  `ym:s:<attribution>TrafficSource`, `ym:s:<attribution>SourceEngine`, `ym:s:<attribution>DirectPlatformType` |  `ym:s:visits`, `ym:s:ecommercePurchases`, `ym:s:productPurchasedUniq`, `ym:s:ecommerce<currency>ConvertedRevenue`, `ym:s:ecommerce<currency>ConvertedRevenuePerVisit`, `ym:s:ecommerce<currency>ConvertedRevenuePerPurchase`, `ym:s:usersPurchasePercentage`  
`coupon` |  Промокоды |  `ym:s:purchaseCoupon` |  `ym:s:visits`, `ym:s:ecommercePurchases`, `ym:s:productPurchasedUniq`, `ym:s:ecommerce<currency>ConvertedRevenue`, `ym:s:ecommerce<currency>ConvertedRevenuePerPurchase`, `ym:s:ecommerce<currency>ConvertedRevenue`, `ym:s:usersPurchasePercentage`  
`basket_products` |  Заказанные товары |  `ym:s:productName` |  `ym:s:productPurchasedQuantity`, `ym:s:productPurchased<currency>ConvertedPrice`, `ym:s:productPurchasedUniq`  
`product_list` |  Списки товаров |  `ym:s:productList`, `ym:s:productPosition`, `ym:s:productName` |  `ym:s:visits`, `ym:s:productInListImpressions`, `ym:s:productInListImpressionsUniq`, `ym:s:productClicks`, `ym:s:productClicksUniq`, `ym:s:productClicksUserPercentage`, `ym:s:productBasketsQuantity`  
`promo_campaigns` |  Промокампании |  `ym:s:EPromotionName`, `ym:s:EPromotionCreative`, `ym:s:EPromotionPosition`, `ym:s:EPromotionCreativeSlot` |  `ym:s:visits`, `ym:s:ePromotionImpressions`, `ym:s:ePromotionImpressionsUniq`, `ym:s:ePromotionImpressionsUserPercentage`, `ym:s:ePromotionClicks`, `ym:s:ePromotionClicksUniq`, `ym:s:ePromotionClicksUserPercentage`  
`ecom_funnel` |  Ecom воронка |  `ym:s:isNewUser` |  `ym:s:users`, `ym:s:productInListImpressionsUniq`, `ym:s:productClicksUniq`, `ym:s:productImpressionsUniq`, `ym:s:productBasketsUniq`, `ym:s:productBeginCheckoutUniq`, `ym:s:productPurchasedUniq`  
`hidden_metrics_goal` |  |  |  `ym:s:productBasketsPrice`, `ym:s:productBasketsRemovePrice`, `ym:s:productPurchasedPrice`, `ym:s:ecommerceRevenue`, `ym:s:ecommerceRevenuePerVisit`, `ym:s:ecommerceRevenuePerPurchase`  
  
### Была ли статья полезна?

ДаНет

Предыдущая

[Содержание](preset_content.md)

Следующая

[Технологии](preset_tech.md)