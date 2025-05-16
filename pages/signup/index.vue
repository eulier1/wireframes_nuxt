<template>
    <div class="min-h-screen flex flex-col items-center justify-center bg-gray-50 px-4">
      <div class="w-full max-w-xs bg-white rounded-2xl shadow p-6">
        <!-- Title -->
        <h1 class="text-xl font-semibold text-center mb-6">Sign up</h1>
  
        <!-- Phone input -->
        <label class="block text-sm text-gray-700 mb-1 font-bold" for="phone">Enter your phone number</label>
        <div class="flex items-center gap-2 w-full max-w-xs">
            <!-- Country code selector -->
            <div class="flex items-center px-3 py-2 border border-gray-300 rounded-md bg-white text-gray-700">
                <UIcon name="i-twemoji-flag-for-flag-israel" class="mr-1 text-gray-400" />
                <span class="font-medium">+972</span>
            </div>
            <!-- Phone number input -->
            <input
            type="tel"
            placeholder="Phone number"
            style="width: inherit"
            class="flex px-3 py-2 border border-gray-300 rounded-md bg-white text-gray-700 outline-none focus:ring-2 focus:ring-primary-500"
            >
        </div>
        <p class="text-xs text-gray-400 mb-4">We will send you a verification code to this number.</p>
  
        <!-- Sign up button -->
        <button class="w-full bg-gray-400 text-white font-semibold py-2 rounded-lg mb-4" disabled>Sign up</button>
  
        <!-- Divider -->
        <div class="flex items-center my-4">
          <div class="flex-1 border-t border-gray-200"/>
          <span class="mx-2 text-xs text-gray-400">OR</span>
          <div class="flex-1 border-t border-gray-200"/>
        </div>
  
        <!-- Social sign up buttons -->
        <div class="flex flex-col gap-2 mb-4">
          <button class="w-full flex items-center gap-2 bg-gray-200 text-gray-800 font-medium py-2 rounded-lg">
            <UIcon class="w-10 px-5 text-lg" name="i-simple-icons-apple" /> 
            <div class="flex w-full justify-center">Sign up with Apple</div>
          </button>
          <button class="w-full flex items-center gap-2 bg-gray-200 text-gray-800 font-medium py-2 rounded-lg">
            <UIcon class="w-10 px-5 text-lg" name="i-simple-icons-google" /> 
            <div class="flex w-full justify-center">Sign up with Google</div>
          </button>
          <button class="w-full flex items-center gap-2 bg-gray-200 text-gray-800 font-medium py-2 rounded-lg">
            <UIcon class="w-10 px-5 text-lg" name="i-simple-icons-facebook" /> 
            <div class="flex w-full justify-center">Sign up with Facebook</div>
          </button>
          <button class="w-full flex items-center gap-2 bg-gray-200 text-gray-800 font-medium py-2 rounded-lg">
            <UIcon class="w-10 px-5 text-lg" name="i-material-symbols-mail-sharp" /> 
            <div class="flex w-full justify-center">Sign up with Email</div>
          </button>
        </div>
  
        <!-- Terms and privacy -->
        <p class="text-xs text-gray-400 text-center mb-4">
          By continuing, you are agree to the Dishie’s
          <a href="#" class="underline">Terms & Conditions</a> and
          <a href="#" class="underline">Privacy policy</a>.
        </p>
  
        <!-- Log in and guest mode -->
        <div class="flex flex-col items-center gap-1">
          <p class="text-sm text-gray-500">
            Already a user?
            <a href="#" class="underline font-bold">Log in</a>
          </p>
          <p class="text-sm text-gray-500">
            Not ready to sign up?
            <a href="#" class="underline font-bold">Guest mode</a>
          </p>
        </div>
      </div>
    </div>
  </template>