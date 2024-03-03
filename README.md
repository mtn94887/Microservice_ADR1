# Adopting Microservices Architecture to the Hotel booking system 

## Context

What is the issue that we're seeing that is motivating this decision or change?

## Decision

What is the solution that we're proposing and/or doing?

## Rationale

Why do we choose this solution?

## Consequences

Pros – What becomes easier? Cons – What becomes more difficult?

## Sample code

Here are the sample codes for the Hotel Booking System that uses microservices. 

**AuthenticationService.java**
```
public interface AuthenticationService {
    public String authenticateUser(String username, String password);
    public boolean isUserAuthenticated(String token);
    public String logoutUser(String token);
}
```

**BookingService.java**
```
public interface BookingService {
    public String bookRoom(String hotelId, String userId,Booking booking);
    public Booking getBookingById(String bookingId);
    public List<Booking> getAllBooking();
    public String cancelBooking(String bookingId);
    public String completeBooking(String bookingId);
}
```

**PaymentService.java**
```
public interface PaymentService {
    public String makePayment(String userId, Payment payment);
    public Payment getPaymentById(String paymentId);
    public String cancelPayment(String paymentId);
    public String refundPayment(String paymentId);
}
```

**HotelFoodService.java**
```
public interface HotelFoodService {
    public List<FoodItem> getAllFoodItems();
    public FoodItem getFoodItemById(String foodItemId);
    public String orderFood(String userId, String foodItemId, int quantity);
    public String cancelFoodOrder(String orderId);
    public List<String> getAvailableFoodCategories();
    public List<FoodItem> getFoodItemsByCategory(String category);
}
```



