### v2.4.0 (2021-12-08)
* * *

#### Fixes:
* Added return types to all api requests.
* Fixed validation logic for IDparam.
* Included typescript related packages to devDependencies.
* Exposed function chargebee#updateRequestTimeoutInMillis to set custom time out.
* Updated default request timeout to 80000ms.

#### New endpoints:
* payment_sources#update_bank_account have been added in payment_sources resource.
* item_price#item_price_find_applicable_items and item_price#item_price_find_applicable_item_prices have been added in item_price resource.

#### New Attributes:
* hsn_code have been added to the resource addon, item_price and plan.
* first_name, last_name and email have been added to the resource payment_sources.

#### New Resource:
* TaxWithheld has been added.Applicable only for API V2. 

#### New Input parameters:
* hsn_code have been added to addons#create_an_addon, addons#update_an_addon, plan#create_an_plan and plan#update_an_plan  apis.
* bank_account[first_name],bank_account[last_name] and bank_account[email] have been added to payment_sources#update_bank_account api.
* charges[hsn_code] have been added in estimate#Create_Invoice, estimate#Create_Invoice_For_Items, hosted_pages#Checkout_One_Time, hosted_pages#Checkout_One_Time_For_Items, invoice#create_an_invoice, invoice#Create_For_Charge_Items_And_Charges and unbilledCharge#create_an_unbilledCharge apis.
* tax_detail[hsn_code] have been added in item_price#create_an_itemPrice and item_price#update_an_itemPrice apis.
* include_deleted have been added in plan#plan_list and addon#addon_list apis.Applicable only for Product Catalog V1.

#### New Enum values:
* subscription_activated_with_backdating, tax_withheld_recorded, tax_withheld_deleted and tax_withheld_refunded has been added to event_type enum.

### v2.3.0 (2021-10-14)
* * *

#### New Attributes:
* entity_id has been added in order_line_item_discounts resource.

#### New Input parameters:
* line_items[tax5_name], line_items[tax5_amount], line_items[tax6_name], line_items[tax6_amount], line_items[tax7_name], line_items[tax7_amount], line_items[tax8_name], line_items[tax8_amount], line_items[tax9_name],  line_items[tax9_amount], line_items[tax10_name], line_items[tax10_amount] have been added in import_invoice api.
* replace_primary_payment_source has been added in create_subscription_for_customer and create_subscription_for_items apis.

#### New Enum values:
* coupon_expired has been added to event_type enum.
* mollie has been added to gateway enum.
* item_level_discount and document_level_discount has been added to discount_type.

### v2.2.0 (2021-08-16)
* * *
* moved types to dev dependencies.
* made default callback value to undefined to make it optional.

#### New Attributes:
* generated_at has been added in credit_note and invoice resources.
* change_option have been added in quoted_subscription resource.
* changes_scheduled_at has been added in subscription and quoted_subscription resources.
* iin and last4 have been added in transaction resource.

#### New Resource:
* quoted_charge has been added. 

#### New Input parameters:
* invoice_date has been added in estimates##create_subscription_estimate, estimates#estimate_for_creating_a_customer_and_subscription, estimates#estimate_for_creating_a_subscription, estimates#create_subscription_for_a_customer_estimate, estimates#update_subscription_estimate, estimates#estimate_for_updating_a_subscription, estimates#cancel_subscription_estimate, estimates#cancel_subscription_for_items_estimate, estimates#create_invoice_for_items_estimate, estimates#create_invoice_estimate, hosted_pages#checkout_existing_subscription, hosted_pages#create_checkout_to_update_a_subscription, invoices#create_an_invoice, invoices#create_invoice_for_items_and_one-time_charges, subscriptions#create_a_subscription, subscriptions#create_subscription_for_customer, subscriptions#update_a_subscription, subscriptions#create_subscription_for_items, subscriptions#update_subscription_for_items, subscriptions#reactivate_a_subscription, subscriptions#cancel_subscription_for_items and subscriptions#cancel_a_subscription endpoints.
* coupon_ids has been added to invoices#create_invoice_for_a_one-time_charge, invoice#create_invoice_for_a_non-recurring_addon, quotes#create_quote_for_one-time_charges, quotes#edit_quote_for_one-time_charges, quotes#create_a_quote_for_charge_and_charge_items, quotes#edit_quote_for_charge_items_and_charges endpoints.
* change_option and changes_scheduled_at have been added in quotes#create_quote_for_updating_a_subscription, quotes#edit_quote_for_updating_a_subscription, quotes#create_a_quote_for_update_subscription_items, quotes#edit_update_subscription_quote_for_items, subscriptions#update_a_subscription and subscriptions#create_subscription_for_items endpoints.
* invoice_date, create_pending_invoices and first_invoice_pending have been added in quotes#convert_a_quote endpoint.
* subscription[auto_close_invoices] has been added in quotes#convert_a_quote endpoint.

#### New Enum values:
* subscription_cancel has been added to charge_event enum in quote_line_groups resource.
* subscription_created_with_backdating, subscription_changed_with_backdating, subscription_canceled_with_backdating, subscription_reactivated_with_backdating, invoice_generated_with_backdating and credit_note_created_with_backdating have been added to event_type enum 
* change_option enum has been added.

#### Deprecated parameters:
* coupon has been deprecated in invoices#create_invoice_for_a_one-time_charge and invoices#create_invoice_for_a_non-recurring_addon endpoints.

### v2.1.0 (2021-07-22)
* * *
#### Fixes:
* Changed use of deprecated Buffer allocation from `new Buffer()` to `Buffer.from()`.
#### New endpoints:
* hosted_pages#checkout_one_time_for_items and hosted_pages#checkout_gift_for_items have been added in hosted_pages resource. 
* orders#resend_an_order has been added in orders resource.
* quotes#edit_create_subscription_quote_for_items, quotes#edit_update_subscription_quote_for_items and quotes#edit_quote_for_charge_items_and_charges have been added in quotes resource. Applicable only for Product Catalog V2.

#### New attributes:
* accounting_category3 and accounting_category4 have been added to addon, item_price and plan resources. 
* quantity_in_decimal has been added to attached_item resource.
* period and period_unit have been added to coupon resource.
* entity_id has been added to line_item_discounts object of credit_note, credit_note_estimate, invoice, invoice_estimate, quote and quote_line_group resources. 
* vat_number_prefix has been added to credit_note, customer, invoice and quote resources.
* price_in_decimal has been added to differential_price and item_price resources. 
* exchange_rate and new_sales_amount have been added to invoice resource.
* archived_at has been added to item and item_price resources.
* trial_end_action has been added to item_price, plan, subscription and subscription_estimate resources.
* resent_orders, tracking_url, resent_status, is_resent, original_order_id and resend_reasons have been added to order resource. 
* line_item_tiers have been added to quote resource.
* plan_quantity_in_decimal and plan_unit_price_in_decimal have been added to quoted_subscription and subscription resources. Applicable only for Product Catalog V1.
* contract_term_billing_cycle_on_renewal and quoted_contract_term have been added to quoted_subscription resource.
* quantity_in_decimal, metered_quantity, last_calculated_at, unit_price_in_decimal, amount_in_decimal and free_quantity_in_decimal have been added to subscription_items object of quoted_subscription and subscription resources.
* starting_unit_in_decimal, ending_unit_in_decimal and price_in_decimal have been added to item_tiers object in quoted_subscription resources.
* cancel_schedule_created_at has been added to subscription resource.
* exchange_rate and merchant_reference_id have been added to transaction resource.

#### New parameters:
* accounting_category3 and accounting_category4 have been added in addons#create_an_addon, addons#update_an_addon, plans#create_a_plan and plans#update_a_plan endpoints.
* quantity_in_decimal has been added in attached_items#create_an_attached_item, attached_items#update_an_attached_item and gifts#create_a_gift_subscription_for_items endpoints.
* period and period_unit have been added in coupons#create_a_coupon, coupons#update_a_coupon, coupons#create_a_coupon_for_items and coupons#update_a_coupon_for_items endpoints.
* vat_number_prefix has been added in customers#create_a_customer, customers#update_billing_info_for_a_customer, estimates#create_subscription, estimates#create_subscription_estimate, estimates#create_subscription_for_items, estimates#create_subscription_for_items_estimate, estimates#update_subscription_for_items, estimates#update_subscription, hosted_pages#checkout_new_subscription, hosted_pages#checkout_one-time_payments, hosted_pages#create_checkout_for_a_new_subscription hosted_pages#checkout_existing_subscription, hosted_pages#create_checkout_to_update_a_subscription, invoices#import_invoice, invoices#update_invoice_details, subscriptions#create_a_subscription, subscriptions#update_a_subscription, subscriptions#update_subscription_for_items and subscriptions#import_a_subscription endpoints.
* payment_method[additional_information] has been added in customers#create_a_customer, customers#update_payment_method_for_a_customer,  customers#collect_payment_for_customer, invoices#create_an_invoice, invoices#create_invoice_for_items_and_one-time_charges, subscriptions#create_a_subscription, subscriptions#update_a_subscription, subscriptions#update_subscription_for_items and subscriptions#import_a_subscription endpoints.
* card[additional_information] has been added in customers#create_a_customer, customers#collect_payment_for_customer, invoices#create_an_invoice, invoices#create_invoice_for_items_and_one-time_charges, payment_sources#create_a_card_payment_source, subscriptions#create_a_subscription, subscriptions#update_a_subscription, subscriptions#update_subscription_for_items and subscriptions#import_a_subscription endpoints.
* bank_account[billing_address] has been added in customers#create_a_customer, invoices#create_an_invoice, invoices#create_invoice_for_items_and_one-time_charges, payment_sources#create_a_bank_account_payment_source and subscriptions#create_a_subscription endpoints.
* price_in_decimal has been added in differential_prices#create_a_differential_price and differential_prices#update_a_differential_price endpoints.
* tiers[starting_unit_in_decimal][0..N], tiers[ending_unit_in_decimal][0..N] and tiers[price_in_decimal][0..N] have been added in differential_prices#create_a_differential_price, differential_prices#update_a_differential_price, item_prices#create_an_item_price and item_prices#update_an_item_price endpoints.
* remove_general_note and notes_to_remove been added in estimates#create_invoice_estimate, estimates#create_invoice_for_items_estimate and invoices#create_invoice_for_items_and_one-time_charges endpoints.
* trial_end_action has been added in estimates#create_subscription, estimates#create_subscription_estimate, estimates#create_subscription_for_items, estimates#create_subscription_for_items_estimate, estimates#update_subscription_for_items, estimates#update_subscription, plans#create_a_plan, plans#update_a_plan, item_prices#create_an_item_price, item_prices#update_an_item_price, subscriptions#create_a_subscription, subscriptions#create_subscription_for_customer, subscriptions#create_subscription_for_items, subscriptions#update_a_subscription and subscriptions#update_subscription_for_items endpoints.
* subscription_items[unit_price_in_decimal][0..N], item_tiers[starting_unit][0..N], item_tiers[ending_unit][0..N] and item_tiers[price_in_decimal][0..N] have been added in estimates#create_subscription_for_items, estimates#create_subscription_for_items_estimate, estimates#update_subscription_for_items, estimates#update_subscription, estimates#cancel_subscription_for_items_estimate, hosted_pages#create_checkout_for_a_new_subscription, hosted_pages#create_checkout_to_update_a_subscription, subscriptions#create_subscription_for_items, subscriptions#update_subscription_for_items and subscriptions#import_subscription_for_items endpoints.
* subscription_items[quantity_in_decimal][0..N] has been added in estimates#create_subscription_for_items, estimates#create_subscription_for_items_estimate, estimates#cancel_subscription_for_items_estimate, estimates#update_subscription_for_items, estimates#update_subscription, estimates#gift_subscription_for_items, estimates#cancel_subscription_for_items_estimate, gifts#create_a_gift_subscription_for_items, hosted_pages#create_checkout_for_a_new_subscription, hosted_pages#create_checkout_to_update_a_subscription, subscriptions#create_subscription_for_items, subscriptions#update_subscription_for_items, subscriptions#import_subscription_for_items and subscriptions#cancel_subscription_for_items endpoints.
* notes_to_remove[entity_type][0..N] and notes_to_remove[entity_id][0..N] have been added in estimates#create_invoice, estimates#create_invoice_for_items and invoices#create_invoice_for_items_and_one-time_charges endpoints.
* item_prices[quantity_in_decimal][0..N] and item_prices[unit_price_in_decimal][0..N] have been added in estimates#create_invoice_for_items, invoices#create_invoice_for_items_and_one-time_charges and unbilled_charges#create_unbilled_charges_for_a_subscription endpoints.
* item_tiers[starting_unit_in_decimal][0..N], item_tiers[ending_unit_in_decimal][0..N] and item_tiers[price_in_decimal][0..N] have been added in estimates#create_invoice_for_items, invoices#create_invoice_for_items_and_one-time_charges and unbilled_charges#create_unbilled_charges_for_a_subscription endpoints.
* payment_intent[additional_information] has been added in customers#create_a_customer, customers#collect_payment_for_customer, gifts#create_a_gift_subscription_for_items, gifts#create_a_gif and payment_sources#create_using_payment_intent endpoints.
* invoice_note has been added in hosted_pages#checkout_one-time_payments endpoint.
* allow_offline_payment_methods has been added in hosted_pages#create_checkout_for_a_new_subscription and hosted_pages#create_checkout_to_update_a_subscription endpoints.
* free_quantity_in_decimal, price_in_decimal and trial_end_action have been added in item_prices#create_an_item_price and item_prices#update_an_item_price endpoints.
* tracking_url has been added in orders#create_an_order, orders#update_an_order and orders#import_an_order endpoints.
* additional_information has been added in payment_sources#create_using_gateway_temporary_token and payment_sources#create_using_permanent_token endpoints.

#### New enum values:
* bancontact has been added to card_type enum.
* card and latam_local_card have been added to powered_by enum.
* item_level_discount and document_level_discount have been added to entity_type enum of credit_note_discount, credit_note_estimate_discount, invoice_discount, line_item_discount and invoice_estimate_discount resources.
* item_level_discount and document_level_discount have been added to discount_type enum.
* add_usages_reminder and order_resent have been added to event_type enum.
* ingenico_direct and exact have been added to gateway enum. 
* max_usage has been added to usage_calculation enum.
* trial_end_action enum has been added.
* order_resent has been added to cancellation_reason enum.
* resent_status enum has been added.
* custom_discount has been added in discount_type enum of order_line_item_discount. 

#### New filter parameters:
* resent_status, is_resent and original_order_id filter parameters have been added in exports#orders and orders#list_orders enpoints.
* updated_at filter parameter has been added in exports#item_families and item_families#list_item_families endpoints.

#### New sort parameters:
* name, id and updated_at sort parameters are added to items#list_items and item_prices#list_item_prices endpoints.
* created_at and updated_at sort parameters are added to payment_sources#list_payment_sources endpoint.
* usage_date sort parameter has been added to usages#list_usages endpoint.

#### Deprecated parameters:
* duration_month parameter has been deprecated in coupon resource.

### v2.0.9 (2021-03-31)
* * *
* Bug fix: Issue with request parameters serialization

### v2.0.8 (2021-01-19)
* * *
##### New resources:
* Usages is added. Applicable only for Product Catalog V2

##### New end points:
* hosted_pages#checkout_one-time_payments has been added in hosted_pages resource

##### New attributes:
* auto_close_invoices has been added to customers, subscriptions resources
* metered, usage_calculation have been added to items resources
* create_pending_invoices, auto_close_invoices have been added to subscriptions resources

##### New parameters:
* auto_close_invoices has been added to the endpoint: customers#create_a_customer, customers#list_customers, customers#update_a_customer
* invoice_allocations[invoice_id] has been added to the endpoint: customers#collect_payment_for_customer
* coupon_ids has been added to the endpoint: estimates#create_invoice_for_items_estimate. Applicable only for Product Catalog V2
* subscription[auto_close_invoices] has been added to the endpoint: exports#export_revenue_recognition_reports, exports#export_deferred_revenue_reports, exports#export_subscriptions
* customer[auto_close_invoices] has been added to the endpoint: exports#export_revenue_recognition_reports, exports#export_deferred_revenue_reports, exports#export_customers
* item[metered], item[usage_calculation] have been added to the endpoint: exports#export_items. Applicable only for Product Catalog V2
* subscription_id has been added to the endpoint: invoices#add_one-time_charge_to_a_pending_invoice, invoices#add_non-recurring_addon_to_a_pending_invoice
* subscription_id has been added to the endpoint: invoices#add_a_charge-item_to_a_pending_invoice. Applicable only for Product Catalog V2
* metered, usage_calculation have been added to the endpoint: items#create_an_item, items#list_item. Applicable only for Product Catalog V2
* create_pending_invoices, auto_close_invoices, first_invoice_pending have been added to the endpoint: subscriptions#create_subscription_for_items, subscriptions#update_subscription_for_items,subscriptions#import_subscription_for_items. Applicable only for Product Catalog V2
* create_pending_invoices, auto_close_invoices have been added to the endpoint: subscriptions#list_subscriptions

### v2.0.7 (2020-12-15)
* * *
##### New end points:
* estimate_for_creating_a_customer_and_subscription, cancel_subscription_for_items_estimate, gift_subscription_estimate_for_items have been added in estimate resource. Applicable only for Product Catalog V2
* regenerate_invoice_estimate has been added in estimate resource
* create_a_gift_subscription_for_items has been added in gift resource. Applicable only for Product Catalog V2
* regenerate_invoice has been added in subscription resource

##### New attributes:
* show_description_in_invoices, show_description_in_quotes have been added to the resource item_prices
* tiers[starting_unit_in_decimal], tiers[ending_unit_in_decimal], tiers[price_in_decimal] have been added to the resource differential_prices
* show_description_in_invoices, show_description_in_quotes have been added to the resource item_prices. Applicable only for Product Catalog V2

##### New parameters:
* payment_intent[additional_info] has been added to the endpoints customers#create_a_customer, invoices#create_an_invoice, payment_sources#create_using_payment_intent, subscriptions#create_a_subscription, subscriptions#update_a_subscription, subscriptions#create_subscription_for_customer, subscriptions#reactivate_a_subscription, subscriptions#resume_a_subscription
* payment_intent[additional_info] has been added to the endpoints gifts#create_a_gift_subscription_for_items, invoices#create_invoice_for_items_and_one-time_charges, subscriptions#create_subscription_for_items, subscriptions#update_subscription_for_items. Applicable only for Product Catalog V2
* contract_term[action_at_term_end], contract_term[cancellation_cutoff_period], subscription[contract_term_billing_cycle_on_renewal] has been added to the endpoint estimates#estimate_for_creating_a_subscription. Applicable only for Product Catalog V2
* cancel_at, contract_term_cancel_option, cancel_reason_code have been added to the endpoint estimates#cancel_subscription_for_items_estimate
* event_based_addons has been added to the endpoint estimates#cancel_subscription_for_items_estimate
* redirect_url has been added to the endpoint hosted_pages#accept_a_quote
* token_id, retain_payment_source, card, bank_account, payment_method added have been added to the endpoint invoices#create_an_invoice
* token_id, retain_payment_source, card, bank_account, payment_method added have been added to the endpoint invoices#create_invoice_for_items_and_one-time_charges. Applicable only for Product Catalog V2
* show_description_in_invoices, show_description_in_quotes have been added to the endpoints item_prices#create_an_item_price, item_prices#update_an_item_price. Applicable only for Product Catalog V2

### v2.0.6 (2020-11-26)
* * *
##### New resources:
item_family, item, item_price, attached_item and differential_price are added. Applicable only for Product Catalog V2

##### New end points:
* coupons#create_a_coupon_for_items and coupons#update_a_coupon_for_items have been added in coupon resource. Applicable only for Product Catalog V2
* estimates#estimate_for_creating_a_subscription, estimates#estimate_for_updating_a_subscription and estimates#create_invoice_for_items_estimate have been added in estimate resource. Applicable only for Product Catalog V2
* estimates#advance_invoice_estimate has been added in estimate resource
* exports#export_item_families, exports#export_items, exports#export_item_prices, exports#export_attached_items and exports#export_differential_price have been added in export api. Applicable only for Product Catalog V2
* checkout_new_for_items and checkout_existing_for_items have been added in hosted_pages api. Applicable only for Product Catalog V2
* invoices#create_invoice_for_items_and_one-time_charges, invoices#create_invoice_for_a_charge-item and invoices#add_a_charge-item_to_a_pending_invoice have been added in invoice resource. Applicable only for Product Catalog V2
* quotes#create_a_quote_for_a_new_subscription_items, quotes#create_a_quote_for_update_subscription_items and quotes#create_a_quote_for_charge_and_charge_items have been added in quote resource. Applicable only for Product Catalog V2
* subscriptions#create_subscription_for_items, subscriptions#update_subscription_for_items, subscriptions#import_subscription_for_items and subscriptions#cancel_subscription_for_items have been added in subscription resource. Applicable only for Product Catalog V2
* subscriptions#edit_advance_invoice_schedule, subscriptions#retrieve_advance_invoice and subscriptions#remove_an_advance_invoice_schedules have been added in subscription resource
* unbilled_charges#create_an_invoice_for_unbilled_charges has been added to unbilled_charge resource

##### New attributes:
* item_constraints and item_constraint_criteria have been added in coupon resource. Applicable only for Product Catalog V2
* success_url and failure_url have been added in payment_intent resource
* subscription_items and item_tiers have been added in quoted_subscription resource. Applicable only for Product Catalog V2
* has_scheduled_advance_invoices has been added in subscription resource
* subscription_items, item_tiers and charged_items have been added in subscription resource. Applicable only for Product Catalog V2

##### New parameters:
* item_id and item_price_id have been added to the end point: subscriptions#list_subscriptions, exports#export_revenue_recognition_reports, exports#export_deferred_revenue_reports, exports#export_subscriptions. Applicable only for Product Catalog V2
* invoice_immediately, schedule_type and fixed_interval_schedule have been added to the end point: subscriptions#charge_future_renewals
*  success_url and failure_url have been added to the end points: payment_intents#create_a_payment_intent, payment_intents#update_a_payment_intent

##### New Enum values:
* PLAN_ITEM_PRICE, ADDON_ITEM_PRICE, CHARGE_ITEM_PRICE are added to Entitytype Enum
* ITEM_FAMILY_CREATED, ITEM_FAMILY_UPDATED, ITEM_FAMILY_DELETED, ITEM_CREATED, ITEM_UPDATED, ITEM_DELETED, ITEM_PRICE_CREATED, ITEM_PRICE_UPDATED, ITEM_PRICE_DELETED, ATTACHED_ITEM_CREATED, ATTACHED_ITEM_UPDATED, ATTACHED_ITEM_DELETED, DIFFERENTIAL_PRICE_CREATED, DIFFERENTIAL_PRICE_UPDATED, DIFFERENTIAL_PRICE_DELETED are added to EventType Enum

### v2.0.5 (2020-11-16)
* * *
* New attributes price_in_decimal, tiers[starting_unit_in_decimal], tiers[ending_unit_in_decimal], tiers[price_in_decimal] have been added to the resource addon
* New input parameters price_in_decimal, tiers[starting_unit_in_decimal], tiers[ending_unit_in_decimal], tiers[price_in_decimal] have been added to addons#create_an_addon, addons#update_an_addon apis.
* New attributes unit_amount_in_decimal, quantity_in_decimal, amount_in_decimal, line_item_tiers[starting_unit_in_decimal], line_item_tiers[ending_unit_in_decimal], line_item_tiers[quantity_used_in_decimal], line_item_tiers[unit_amount_in_decimal] have been added to the resources credit_note, credit_note_estimate, invoice, invoice_estimate
* New input parameters line_items[unit_amount_in_decimal], line_items[quantity_in_decimal] have been added to credit_notes#create_credit_note api.
* New input parameters subscription[plan_unit_price_in_decimal], subscription[plan_quantity_in_decimal], addons[quantity_in_decimal], addons[unit_price_in_decimal], event_based_addons[quantity_in_decimal], event_based_addons[unit_price_in_decimal] have been added to estimates#create_subscription_estimate, estimates#create_subscription_for_a_customer_estimate, estimates#update_subscription_estimate, hosted_pages#checkout_new_subscription, hosted_pages#checkout_existing_subscription, quotes#create_a_quote_for_a_new_subscription,  quotes#edit_create_subscription_quote, quotes#create_a_quote_for_update_subscription, quotes#edit_update_subscription_quote,  apis
* New input parameters subscription[plan_quantity_in_decimal], addons[quantity_in_decimal] have been added to estimates#gift_subscription_estimate, gifts#create_a_gift, hosted_pages#checkout_gift_subscription apis
* New input parameters addons[quantity_in_decimal], addons[unit_price_in_decimal], charges[amount_in_decimal] have been added to estimates#create_invoice_estimate, invoices#create_an_invoice, quotes#create_a_quote_for_one-time_charges, quotes#edit_one-time_quote apis
* New input parameter amount_in_decimal has been added to invoices#create_invoice_for_a_one-time_charge api
* Input parameter amount has been made optional to invoices#create_invoice_for_a_one-time_charge api
* New input parameters addon_quantity_in_decimal, addon_unit_price_in_decimal have been added to invoices#create_invoice_for_a_non-recurring_addon
* New input parameters line_items[unit_amount_in_decimal], line_items[quantity_in_decimal], line_items[amount_in_decimal], line_item_tiers[starting_unit_in_decimal], line_item_tiers[ending_unit_in_decimal], line_item_tiers[quantity_used_in_decimal], line_item_tiers[unit_amount_in_decimal] have been added to invoices#import_invoice api
* Input parameters line_item_tiers[starting_unit], line_item_tiers[ending_unit], line_item_tiers[quantity_used], line_item_tiers[unit_amount] have beed made optional in invoices#import_invoice api
* New input parameters addon_quantity_in_decimal, addon_unit_price_in_decimal have been added to invoices#add_non-recurring_addon_to_a_pending_invoice api
* New input parameter invoice_date has been added to invoices#close_a_pending_invoice api
* New attributes tiers[starting_unit_in_decimal], tiers[ending_unit_in_decimal], tiers[price_in_decimal], attached_addons[quantity_in_decimal], event_based_addons[quantity_in_decimal], free_quantity_in_decimal, price_in_decimal have been added to the resource plan
* New input parameters tiers[starting_unit_in_decimal], tiers[ending_unit_in_decimal], tiers[price_in_decimal], attached_addons[quantity_in_decimal], event_based_addons[quantity_in_decimal], free_quantity_in_decimal, price_in_decimal have been added to plans#create_a_plan, plans#update_a_plan apis
* New attribute amount_in_decimal has been added to the resource promotional_credit
* New input parameter amount_in_decimal has been added to promotional_credits#add_promotional_credits, promotional_credits#deduct_promotional_credits, promotional_credits#set_promotional_credits apis
* Input parameter amount has been made optional in promotional_credits#add_promotional_credits, promotional_credits#deduct_promotional_credits, promotional_credits#set_promotional_credits apis
* New attributes unit_amount_in_decimal, quantity_in_decimal, amount_in_decimal have been added to the resource quote
* New attributes addons[quantity_in_decimal], addons[unit_price_in_decimal], addons[amount_in_decimal], event_based_addons[quantity_in_decimal], event_based_addons[unit_price_in_decimal] have been added to the sub resource quoted_subscription
* New attributes unit_amount_in_decimal, quantity_in_decimal, amount_in_decimal have been added to the sub resource quoted_line_group
* New attributes addons[quantity_in_decimal], addons[unit_price_in_decimal], addons[amount_in_decimal], event_based_addons[quantity_in_decimal], event_based_addons[unit_price_in_decimal], plan_free_quantity_in_decimal, plan_quantity_in_decimal, plan_unit_price_in_decimal, plan_amount_in_decimal have been added to the resource subscription
* New input parameters plan_unit_price_in_decimal, plan_quantity_in_decimal, addons[quantity_in_decimal], addons[unit_price_in_decimal], event_based_addons[quantity_in_decimal], event_based_addons[unit_price_in_decimal] have been added to subscriptions#create_a_subscription, subscriptions#create_subscription_for_customer, subscriptions#update_a_subscription, subscriptions#import_a_subscription, subscriptions#import_subscription_for_customer apis
* New input parameter amount_in_decimal has been added to subscriptions#add_charge_at_term_end apis
* Input parameter amount has been made optional in subscriptions#add_charge_at_term_end apis
* New input parameters addon_quantity_in_decimal, addon_unit_price_in_decimal have been added to subscriptions#charge_addon_at_term_end api
* New attributes tiers[starting_unit_in_decimal], tiers[ending_unit_in_decimal], tiers[quantity_used_in_decimal], tiers[unit_amount_in_decimal], unit_amount_in_decimal, quantity_in_decimal, amount_in_decimal have been added to the resource unbilled_charge
* New endpoint transactions#refund_a_payment has been added to the resource transaction
### v2.0.4 (2020-10-19)
* * *
* New optional attribute quoted_subscriptions has been added to the resource quote
* New optional attributes resource_version and updated_at are added to the resource payment_intent
### v2.0.3 (2020-09-29)
* * *

* New attribute included_in_mrr has been added in addon and coupon resource
* New attribute offline_payment_method has been added in subscription and customer resource
* New input parameter included_in_mrr has been added in create_an_addon, update_an_addon, create_a_coupon and update_a_coupon apis.
* New input parameter offline_payment_method has been added in create_a_customer, list_customers, update_a_customer, create_a_subscription, create_subscription_for_customer and list_subscriptions apis
* New input parameter auto_collection has been added in update_a_subscription
* New input parameter subscription[offline_payment_method] has been added in create_subscription_estimate, create_subscription_for_a_customer_estimate, update_subscription_estimate, export_revenue_recognition_reports, export_deferred_revenue_reports, export_subscriptions, checkout_new_subscription and checkout_existing_subscription apis
* New input parameter subscription[auto_collection] has been added in checkout_existing_subscription and update_subscription_estimate apis
* New input parameter customer[offline_payment_method] has been added in export_revenue_recognition_reports, export_deferred_revenue_reports, export_customers and create_a_subscription

### v2.0.2 (2020-09-09)
* * *

* New input parameter currency_code is added in list_addons, list_coupons, list_plans, export_plans, export_addons, export_coupons apis
* New attributes powered_by has been added in card resource
* New input parameters subscription[free_period], subscription[free_period_unit] have been added in create_subscription_estimate, create_subscription_for_a_customer_estimate, update_subscription_estimate apis
* Input parameter invoice[customer_id] is made optional in create_invoice_estimate api
* Input parameter customer_id is made optional in create_an_invoice
* Attribute created_at in dunning_attempts is made optional in the invoice resource
* New attributes free_period and free_period_unit have been added in the Subscription resource
* New enum type free_period_unit has been added with the values:
	DAY,
	WEEK,
	MONTH,
	YEAR
* New enum type powered_by has been added in card resource with the values: 
	IDEAL,
    SOFORT,
    BANCONTACT,
    GIROPAY,
    NOT_APPLICABLE
* New endpoint import_contract_term has been added to the subscription resource
* Attributes status, amount and date inside the linked_payment are made optional in the transaction resource
* New endpoint delete has been added to the virtual_bank_account resource
* New values GIROPAY and DOTPAY have been added to the payment_method_types enum
* New values PAYMENT_SOURCE_EXPIRING and PAYMENT_SOURCE_EXPIRED have been added to the event_type enums
* New value PAYPAL has been added to the gateway enum

### v2.0.1 (2020-07-15)
* * * 

* New attributes show_description_in_invoices, show_description_in_quotes have been added in Addon, Plan resource
* New input parameters show_description_in_invoices, show_description_in_quotes have been added for create_an_addon, update_an_addon, create_a_plan, update_a_plan apis
* New attribute create_reason_code has been added in Credit notes resource
* Attribute reason_code is made optional in the Credit notes resource
* New filter parameter create_reason_code is added in list_credit_notes api
* New input parameter refund_reason_code has been added in Credit notes' Refund, Record a refund apis
* Sub-resources parent_account_access and child_account_access have been added in Customer resource
* New attribute use_default_hierarchy_settings has been added in Customer resource
* New endpoint update_hierarchy_settings has been added in Customer resource
* New input parameters use_default_hierarchy_settings,  parent_account_access, child_account_access have been added in link_a_customer api
* New input parameter invoice_notes, coupon_ids, invoice[subscription_id], charges[taxable], charges[tax_profile_id], charges[avalara_tax_code], charges[taxjar_product_code] has been added to create_invoice_estimate api
* New input param cancel_reason_code has been added to export_revenue_recognition_reports, export_deferred_revenue_reports, export_subscriptions, export_credit_notes apis
* New input param coupon_ids has been added to checkout_new_subscription, checkout_existing_subscription apis
* Input param subscription_coupon has been deprecated in checkout_new_subscription, checkout_existing_subscription apis
* New attribute void_reason_code has been added to the Invoice resource
* Attribute cn_reason_code has been made optional in applied_credits, adjustment_credit_notes, issued_credit_notes, linked_credit_note sub-resources
* New attribute cn_create_reason_code has been added in applied_credits, adjustment_credit_notes, issued_credit_notes, linked_credit_note sub-resources
* New input parameter subscription_id, invoice_note, remove_general_note, coupon_ids, charges[taxable], charges[tax_profile_id], charges[avalara_tax_code], charges[taxjar_product_code] have been added to create_an_invoice api
* Input parameter coupon is deprecated from create_an_invoice api
* New filter parameter void_reason_code has been added to list_invoices api
* New input parameter invoice_note, remove_general_note, notes_to_remove[entity_type], notes_to_remove[entity_id] have been added to close_a_pending_invoice api
* New input parameter void_reason_code has been added to void_an_invoice api
* New input parameter credit_note[create_reason_code] has been added to refund_an_invoice, record_refund_for_an_invoice api
* New endpoints import_an_order and delete_an_imported_order have been added to Order resource
* New filter parameter exclude_deleted_credit_notes has been added to list_orders api
* New attribute payment_method_type has been added to payment_intent resource and active_payment_attempt sub-resource
* New input parameter payment_method_type has been added to create_a_payment_intent, update_a_payment_intent api
* New attributes version, contract_term_start, contract_term_end, contract_term_termination_fee have been added to Quotes resource
* New endpoints edit_create_subscription_quote, edit_update_subscription_quote, edit_one_time_quote, extend_expiry_date have beed added to Quotes resource
* New input parameters contract_term[action_at_term_end], contract_term[cancellation_cutoff_period], subscription[contract_term_billing_cycle_on_renewal] have been added to create_a_quote_for_a_new_subscription, create_a_quote_for_update_subscription apis
* New attribute version has been added to quote_line_group sub-resource
* New attribute cancel_reason_code has been added to Subscriptions resource
* New filter parameter cancel_reason_code has been added to list_subscriptions, cancel_a_subscription apis
* New input parameter contract_term_billing_cycle_on_renewal has been added to import_a_subscription, import_subscription_for_customer apis
* New input parameter event_based_addon has been added to cancel_a_subscription api
* New filter parameter is_voided has been added to list_unbilled_charges api
* New event_types MRR_UPDATED, ORDER_DELETED have been added
* New values SOFORT, BANCONTACT have been added to the payment_method_types enum
* New attributes entity_type_description has been added to the line_items sub-resource

### v2.0.0 (2019-01-10)
 * * *

 Chargebee [API V2](https://apidocs.chargebee.com/docs/api#versions) for typescript is now live!
