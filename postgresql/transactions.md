

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
