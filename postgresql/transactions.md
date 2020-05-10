# Links
- [Уровень изолированности транзакций](https://ru.wikipedia.org/wiki/%D0%A3%D1%80%D0%BE%D0%B2%D0%B5%D0%BD%D1%8C_%D0%B8%D0%B7%D0%BE%D0%BB%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8_%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B9)
## Examples
# Locking row in table (Payment)
```
BEGIN TRANSACTION ISOLATION LEVEL REPEATABLE READ;
LOCK TABLE payments IN ROW EXCLUSIVE MODE;
SELECT * from payments where  id = 2 FOR UPDATE;
UPDATE public.payments
SET status = 'wait_payment'
WHERE id = 2;
COMMIT;
```
