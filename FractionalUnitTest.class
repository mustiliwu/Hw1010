import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.*;

class FractionalUnitTest {

	@Test
	void constructorTest() {
		assertEquals("71/13", new Fractional(71, 13).toString());
		
		assertEquals("3/9", new Fractional(3, 9).toString());
		assertEquals("28/49", new Fractional(28, 49).toString());
		
		assertEquals("28/14", new Fractional(28, 14).toString());
		assertEquals("28/14", new Fractional(-28, -14).toString());
		assertEquals("-28/14", new Fractional(28, -14).toString());
		assertEquals("-28/14", new Fractional(-28, 14).toString());
		
		assertEquals("0", new Fractional(0, 2).toString());
		assertEquals("-0", new Fractional(0, -2).toString());
		
		assertEquals("5", new Fractional(5, 1).toString());
		assertEquals("10/2", new Fractional(10, 2).toString());
		
		assertEquals(Fractional.PositiveInfinity, new Fractional(2, 0).toString()); 
		assertEquals(Fractional.NegativeInfinity, new Fractional(-100, 0).toString());
		
		assertEquals(Fractional.NotANumber, new Fractional(0, 0).toString());
		
		Fractional zero1 = new Fractional(0, 1);
        assertEquals(0, zero1.numerator);
        assertTrue(zero1.denominator > 0);

		Fractional zero2 = new Fractional(0, -1);
        assertEquals(0, zero2.numerator);
        assertTrue(zero2.denominator < 0);		
	}

	@Test
	void simplificationTest() {
		assertEquals("71/13", new Fractional(71, 13).simplify().toString());
		
		assertEquals("1/3", new Fractional(3, 9).simplify().toString());
		assertEquals("4/7", new Fractional(28, 49).simplify().toString());
		
		assertEquals("2", new Fractional(28, 14).simplify().toString());
		assertEquals("2", new Fractional(-28, -14).simplify().toString());
		assertEquals("-2", new Fractional(28, -14).simplify().toString());
		assertEquals("-2", new Fractional(-28, 14).simplify().toString());
		
		assertEquals("0", new Fractional(0, 2).simplify().toString());
		assertEquals("-0", new Fractional(0, -2).simplify().toString());
		
		assertEquals("5", new Fractional(5, 1).simplify().toString());
		assertEquals("5", new Fractional(10, 2).simplify().toString());
		
		assertEquals(Fractional.PositiveInfinity, new Fractional(2, 0).simplify().toString()); 
		assertEquals(Fractional.NegativeInfinity, new Fractional(-100, 0).simplify().toString());
		
		assertEquals(Fractional.NotANumber, new Fractional(0, 0).simplify().toString());
		
		Fractional zero1 = new Fractional(0, 1).simplify();
        assertEquals(0, zero1.numerator);
        assertTrue(zero1.denominator > 0);

		Fractional zero2 = new Fractional(0, -1).simplify();
        assertEquals(0, zero2.numerator);
        assertTrue(zero2.denominator < 0);			
	}

	@Test
	void isNaNTest() {
		assertEquals(Fractional.NotANumber, new Fractional(0, 0).toString());
	}

	@Test
	void isInfinityTest() {
		assertEquals(Fractional.PositiveInfinity, new Fractional(10, 0).toString());
		assertEquals(Fractional.NegativeInfinity, new Fractional(-90, 0).toString());
	}

	@Test
	void signTest() {
		Assertions.assertThrows(ArithmeticException.class, () -> {new Fractional(0, 0).sign(); });		
		
		assertEquals(0, new Fractional(0, 10).sign());
		
		assertEquals(+1, new Fractional(10, 0).sign());
		assertEquals(-1, new Fractional(-10, 0).sign());
		
		assertEquals(+1, new Fractional(10, 5).sign());
		assertEquals(+1, new Fractional(-10, -5).sign());		
		assertEquals(-1, new Fractional(-10, 5).sign());
		assertEquals(-1, new Fractional(10, -5).sign());
	}

	@Test
	void getValueTest() {
		assertEquals(0.0, new Fractional(0, 1).getValue());
		assertEquals(-0.0, new Fractional(0, -1).getValue());

		assertEquals(1.0, new Fractional(1, 1).getValue());
		assertEquals(1.0, new Fractional(-4, -4).getValue());
		assertEquals(0.5, new Fractional(1, 2).getValue());
		assertEquals(-0.5, new Fractional(-1, 2).getValue());
		
		assertTrue(Double.isNaN(new Fractional(0, 0).getValue()));
		assertEquals(Double.POSITIVE_INFINITY, new Fractional(1, 0).getValue());
		assertEquals(Double.NEGATIVE_INFINITY, new Fractional(-2, 0).getValue());
	}
	
	@Test
	void toStringMetodTest() {
		assertEquals("2", new Fractional(2, 1).toString());
		
		assertEquals("7/10", new Fractional(7, 10).toString());
		assertEquals("5/3", new Fractional(5, 3).toString());
		
		assertEquals(Fractional.NotANumber, new Fractional(0, 0).toString());
		assertEquals(Fractional.PositiveInfinity, new Fractional(1, 0).toString());
		assertEquals(Fractional.NegativeInfinity, new Fractional(-1, 0).toString());
	}
	
	@Test
	void equalsMethodTest() {
		assertNotEquals(new Fractional(2, 1), null);
		
		assertNotEquals(new Fractional(0, 0), new Fractional(0, 0));
		
		assertEquals(new Fractional(1, 0), new Fractional(1, 0));
		assertEquals(new Fractional(1, 0), new Fractional(2, 0));
		assertEquals(new Fractional(1, 0), new Fractional(10, 0));
		assertEquals(new Fractional(-1, 0), new Fractional(-100, 0));
		
		assertEquals(new Fractional(0, 1), new Fractional(0, 1));
		assertEquals(new Fractional(0, 1), new Fractional(0, 2));
		
		assertEquals(new Fractional(2, 1), new Fractional(2, 1));
		assertEquals(new Fractional(8, 4), new Fractional(2, 1));
		assertEquals(new Fractional(-8, -4), new Fractional(2, 1));
		assertEquals(new Fractional(-8, 4), new Fractional(2, -1));
		assertEquals(new Fractional(8, -4), new Fractional(2, -1));
		assertEquals(new Fractional(8, -4), new Fractional(-2, 1));
	}

}
