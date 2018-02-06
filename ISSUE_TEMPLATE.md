
## Problem
Write your problem here

### Background
Please add to the problems

#### Story
Please add a story if applicable

```
As a User,
In order to access my funds,
I would like to make a withdrawal.
```

#### Spec
Please write a spec if any between the back ticks

```ruby
  it 'funds are reduced at withdraw' do
    subject.withdraw( 50, '1234', account)
    expect(subject.funds).to eq 950
  end
```
#### Implementation code
Please add your implementation code between the back ticks in the example below 
and change the programming language from ruby to another if neccesary

```ruby
  def withdrawal(amount, pin_code, account)
    case
      when insufficent_funds_in_account(amount, account)
        { status: false, message: 'insufficient funds', date: Date.today }
      when insufficent_funds_in_ATM(amount)
        { status: false, message: 'insufficient funds in ATM', date: Date.today }
      when incorrect_pin?(pin_code, account.pin_code)
        { status: false, message: 'wrong pin', date: Date.today }
      when card_expired?(account.exp_date)
        { status: false, message: 'card expired', date: Date.today }
      else
        perform_the_transaction(amount, account)
    end
  end
```

### Screenshots
Add your screenshots here

### How did you try to solve the problem?
Write the steps you took to try to fix the problem here


### 
Markdown [guide](https://guides.github.com/features/mastering-markdown/)

**Note: PLEASE REMOVE SECTIONS THAT WERE NOT FILLED UP BEFORE YOU SUBMIT YOUR ISSUE. INCLUDING THIS NOTE**
